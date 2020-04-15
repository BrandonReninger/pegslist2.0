<template>
  <div class="job-details container-fluid">
    <div class="row">
      <div class="col-12 text-center">
        <h5>{{job.company}}</h5>
        <h5>{{job.jobTitle}}</h5>
        <p>{{job.description}}</p>
        <p>{{job.hours}}</p>
        <p>{{job.rate}}</p>
        <button class="btn btn-dark m-1" @click="$router.push({name:'Jobs'})">Back</button>
        <button class="btn btn-danger" @click="deleteJob()">Delete</button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "job-details",
  data() {
    return {};
  },
  created() {
    this.$store.dispatch("getJob", this.$route.params.jobId);
  },
  computed: {
    job() {
      return this.$store.state.activeJob;
    }
  },
  methods: {
    deleteJob() {
      this.$router.push({ name: "Jobs" });
      this.$store.dispatch("deleteJob", this.job._id);
    }
  },
  components: {}
};
</script>


<style scoped>
</style>