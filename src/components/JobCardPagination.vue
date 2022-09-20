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

export default {
  name: "JobCardPagintion",
  components: {
    JobCard,
  },
  data() {
    return {
      jobs: [],
      currentPage: 1,
      isLoading: true,
    };
  },
  created() {
    api.getJobs().then((response) => {
      this.jobs = response.data;
      this.isLoading = false;
    });
  },
  computed: {
    perPage() {
      return 8;
    },
    rows() {
      return this.jobs.length;
    },
    jobList() {
      return this.jobs.slice(
        (this.currentPage - 1) * this.perPage,
        this.currentPage * this.perPage
      );
    },
  },
};
</script>
