<template>
  <div class="col-12 col-md-8 bg-info">
    <JobIndexPagination></JobIndexPagination>
  </div>
</template>

<script>
// @ is an alias to /src
import JobIndexPagination from "@/components/JobIndexPagination.vue";

export default {
  name: "JobIndex",
  components: {
    JobIndexPagination,
  },
};
</script>
