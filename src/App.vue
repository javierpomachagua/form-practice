<template>
  <div class="container">
    <form v-if="!isSubmitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->
          <div class="panel panel-default">
            <div class="panel-heading">Login</div>
            <div class="panel-body">
              <div class="form-group">
                <label for="fullname">Fullname:</label>
                <!-- <input type="text" name="fullname" id="fullname" v-model="fullname"> -->
                <fullname v-model="fullname"></fullname>
              </div>
              <div class="form-group">
                <label for="mail">Mail:</label>
                <input type="email" name="mail" id="mail" v-model="mail">
              </div>
              <div class="form-group">
                <label for="password">Password:</label>
                <input type="password" name="password" id="password" v-model="password">
              </div>
              <div class="form-group">
                <label for="password">Store Data?:</label>
                <app-switch v-model="storeData"></app-switch>
              </div>
            </div>
            <div class="panel-footer">
              <button class="btn btn-default" @click.prevent="submitted()">Submit</button>
            </div>
          </div>

          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ fullname }}</p>
            <p>Mail: {{ mail }}</p>
            <p>Password: {{ password }}</p>
            <p>Store in Database?: {{ storeData }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppSwitch from "./Switch.vue";
import Fullname from './Fullname.vue';

export default {
  components: {
    AppSwitch,
    Fullname
  },
  data() {
    return {
      fullname: "",
      email: "",
      password: "",
      storeData: false,
      isSubmitted: false
    };
  },
  methods: {
    submitted() {
      this.isSubmitted = true;
    }
  }
};
</script>

<style>
</style>
