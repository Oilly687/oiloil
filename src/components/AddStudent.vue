<template>
  <div class="submit-form">
    <div v-if="!submitted">
      <div class="form-group">
        <label for="name">Name</label>
        <input
          type="text"
          class="form-control"
          id="name"
          required
          v-model="student.name"
          name="name"
        />
      </div>

      <div class="form-group">
        <label for="idno">ID No</label>
        <input
          class="form-control"
          id="idno"
          required
          v-model="student.idno"
          name="idno"
        />
      </div>

      <button @click="saveStudent" class="btn btn-success">Submit</button>
    </div>

    <div v-else>
      <h4>You submitted successfully!</h4>
      <button class="btn btn-success" @click="newStudent">Add</button>
    </div>
  </div>
</template>

<script>
import StudentDataService from "../services/StudentDataService";

export default {
  name: "add-student",
  data() {
    return {
      student: {
        id: null,
        name: "",
        idno: "",
      },
      submitted: false,
    };
  },
  methods: {
    saveStudent() {
      var data = {
        name: this.student.name,
        idno: this.student.idno,
      };

      StudentDataService.create(data)
        .then((response) => {
          this.student.id = response.data.id;
          console.log(response.data);
          this.submitted = true;
        })
        .catch((e) => {
          console.log(e);
        });
    },

    newStudent() {
      this.submitted = false;
      this.student = {};
    },
  },
};
</script>

<style>
.submit-form {
  max-width: 300px;
  margin: auto;
}
</style>