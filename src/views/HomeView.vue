<template>
  <div class="row">
    <div class="col-12 col-md-4 bg-warning">.col-12 .col-md-8</div>
    <div class="col-12 col-md-8 bg-info">
      <JobCardPagination></JobCardPagination>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import JobCardPagination from "@/components/JobCardPagination.vue";

export default {
  name: "HomeView",
  components: {
    JobCardPagination,
  },
};
</script>
