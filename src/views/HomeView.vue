<template>
  <div class="row">
    <div class="col-12 col-md-4 bg-warning">.col-12 .col-md-8</div>
    <div class="col-12 col-md-8 bg-info">
      <JobIndex></JobIndex>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import JobIndex from "@/components/JobIndex.vue";

export default {
  name: "HomeView",
  components: {
    JobIndex,
  },
};
</script>
