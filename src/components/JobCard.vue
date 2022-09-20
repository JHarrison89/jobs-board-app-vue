<template>
  <b-list-group-item class="d-flex align-items-center">
    <b-avatar
      variant="info"
      src="https://placekitten.com/300/300"
      class="mx-3"
    ></b-avatar>
    <span class="me-auto">{{ job.title }}</span>
    <b-badge>{{ job.id }}</b-badge>
  </b-list-group-item>
</template>

<script>
export default {
  name: "JobCard",
  props: {
    job: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.job-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}

.job-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
