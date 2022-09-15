<template>
  <div class="row">
    <div class="col-12 col-md-4 bg-warning">.col-12 .col-md-8</div>
    <div class="col-12 col-md-8 bg-info">
      <JobCardPagination></JobCardPagination>
    </div>
  </div>

  <div class="home">
    <CardTest />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import CardTest from "@/components/CardTest.vue";
import api from "@/api";
import JobCardPagination from "@/components/JobCardPagination.vue";

export default {
  name: "HomeView",
  components: {
    CardTest,
    JobCardPagination,
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
