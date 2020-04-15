<template>
  <div class="jobs col-12">
    <div class="row">
      <create-job></create-job>
    </div>
  </div>
</template>


<script>
export default {
  name: "jobs",
  data() {
    return {};
  },
  computed: {
    jobs() {
      return this.$store.state.jobs;
    }
  },
  methods: {},
  components: {
    Job
  }
};
</script>


<style scoped>
</style>