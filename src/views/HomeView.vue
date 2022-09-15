<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <JobCard v-for="job in jobs" :key="job.id" :job="job" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import JobCard from "@/components/JobCard.vue";
import api from "@/api";

export default {
  name: "HomeView",
  components: {
    JobCard,
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
