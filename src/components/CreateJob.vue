<template>
  <div class="create-job border col-12">
    <form @submit.prevent="create-job()">
      <div class="form-group">
        <label for="title"></label>
        <input
          type="text"
          name="title"
          class="form-control"
          placeholder="Enter Job Title"
          aria-describedby="helpId"
          v-model="newJob.title"
          required
        />
      </div>
      <div class="form-group">
        <label for="company"></label>
        <input
          type="text"
          name="company"
          class="form-control"
          placeholder="Enter Company Name"
          aria-describedby="helpId"
          v-model="newJob.company"
          required
        />
      </div>
      <div class="form-group">
        <label for="hours"></label>
        <input
          type="number"
          name="hours"
          class="form-control"
          placeholder="Enter Hours/week"
          aria-describedby="helpId"
          v-model="newJob.hours"
          required
        />
      </div>
      <div class="form-group">
        <label for="rate"></label>
        <input
          type="number"
          name="rate"
          class="form-control"
          placeholder="Enter Hourly Rate"
          aria-describedby="helpId"
          v-model="newJob.rate"
          required
        />
        <div class="form-group">
          <label for="description"></label>
          <input
            type="text"
            name="description"
            class="form-control"
            placeholder="Enter Job Description"
            aria-describedby="helpId"
            v-model="newJob.description"
            required
          />
        </div>
      </div>
      <button class="btn btn-lg btn-success"></button>
    </form>
  </div>
</template>


<script>
export default {
  name: "create-job",
  data() {
    return {
      newCar: {}
    };
  },
  computed: {},
  methods: {
    createJob() {
      this.$store.dispatch("createJob", this.newJob);
      this.newJob = {};
    }
  },
  components: {}
};
</script>


<style>
.create-job {
  outline: 1px solid black;
}
</style>