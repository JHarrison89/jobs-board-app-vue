<template>
  <b-list-group>
    <JobCard v-for="job in jobList" :key="job.id" :job="job" />
    <b-pagination
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      aria-controls="itemList"
      align="center"
    ></b-pagination>
  </b-list-group>
</template>

<script>
import JobCard from "@/components/JobCard.vue";
import api from "@/api";
import { ref, computed, onMounted } from "vue";

export default {
  name: "JobCardPagintion",
  components: {
    JobCard,
  },
  setup() {
    const jobs = ref([]);
    const currentPage = ref(1);
    const perPage = 8;
    const rows = computed(() => {
      return jobs.value.length;
    });
    const jobList = computed(() => {
      return jobs.value.slice(
        (currentPage.value - 1) * perPage,
        currentPage.value * perPage
      );
    });

    onMounted(async () => {
      await api.getJobs().then((response) => {
        jobs.value = response.data;
      });
    });

    return {
      jobList,
      currentPage,
      perPage,
      rows,
    };
  },
};
</script>
