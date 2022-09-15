<template>
  <b-list-group>
    <JobCard v-for="job in jobs" :key="job.id" :job="job" />
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
  props: {
    job: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      jobs: [],
      isLoading: true,
    };
  },
  created() {
    api.getJobs().then((response) => {
      this.jobs = response.data;
      this.isLoading = false;
    });
  },
};
</script>
