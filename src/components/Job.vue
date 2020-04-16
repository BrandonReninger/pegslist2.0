<template>
  <div class="job border col-3" @click="selectJob()">
    <h3>{{jobData.jobTitle}}</h3>
    <p>{{jobData.company}}</p>
  </div>
</template>


<script>
export default {
  name: "job",
  props: ["jobData"],
  data() {
    return {};
  },
  //computed: {},
  methods: {
    selectJob() {
      this.$store.commit("setActiveJob", {});
      this.$router.push({
        name: "JobDetails",
        params: { jobId: this.jobData._id }
      });
    }
  }
};
</script>


<style scoped>
</style>