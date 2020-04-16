<template>
  <div class="jobs col-12">
    <div class="row">
      <create-job></create-job>
      <job v-for="job in jobs" :jobData="job" :key="job._id"></job>
    </div>
  </div>
</template>


<script>
import Job from "../components/Job";
import CreatJob from "../components/CreateJob";
export default {
  name: "jobs",
  data() {
    return {};
  },
  computed: {
    jobs() {
      return this.$store.state.jobs;
    },
    created() {
      this.$store.dispatch("getJobs");
    }
  },
  methods: {},
  components: {
    Job,
    CreateJob
  }
};
</script>


<style>
.jobs {
  outline: 1px solid black;
}
</style>