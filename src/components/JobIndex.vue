<template>
  <div class="col-12 col-md-8 bg-info">
    <JobIndexPagination v-if="true"></JobIndexPagination>
    <router-view></router-view>
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
  setup() {
    const renderJobShow = false;
    return { renderJobShow };
  },
};
</script>
