<template>
  <b-list-group>
    <JobIndexRow v-for="job in jobList" :key="job.id" :job="job" />
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
import JobIndexRow from "@/components/JobIndexRow.vue";
import api from "@/api";
import { ref, computed, onMounted } from "vue";

export default {
  name: "JobIndexPagination",
  components: {
    JobIndexRow,
  },
  setup() {
    return paginateJobs();
  },
};

function paginateJobs() {
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
    await api
      .getJobs()
      .then((response) => {
        jobs.value = response.data;
      })
      .catch((error) => {
        console.log(error);
      });
  });

  // onMounted(async () => {
  //   try {
  //     jobs.value = await api.getJobs();
  //   } catch (error) {
  //     console.log(error);
  //   }
  // });

  // onMounted(async () => {
  //   api
  //     .getJobs()
  //     .then((response) => {
  //       jobs.value = response.data;
  //     })
  //     .catch((error) => {
  //       console.log(error);
  //     });
  // });

  return {
    jobList,
    currentPage,
    perPage,
    rows,
  };
}
</script>
