<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 mt-5 offset-md-3">
        <div class="card">
          <div class="card-body">
            <h1 class="h3 mb-3  text-center">Register</h1>
            <form v-on:submit.prevent="register">
              <div class="row">
                <div class="col-md-6">
                  <div class="form-group">
                    <label>Name</label>
                    <input
                      type="text"
                      v-model="name"
                      autocomplete="on"
                      class="form-control"
                      placeholder="Username"
                      value
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label>Username</label>
                    <input
                      type="text"
                      v-model="username"
                      autocomplete="on"
                      class="form-control"
                      placeholder="Username"
                      value
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label>Email</label>
                    <input
                      type="text"
                      v-model="email"
                      autocomplete="on"
                      class="form-control"
                      placeholder="Email"
                    />
                  </div>
                </div>
              </div>

              <div class="row">
                <div class="col-md-6">
                  <div class="form-group">
                    <label>Password</label>
                    <input
                      type="password"
                      autocomplete="on"
                      v-model="password"
                      class="form-control"
                      placeholder
                      value
                    />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="update ml-auto mr-auto">
                  <button type="submit" class="btn btn-primary btn-round">Register</button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import router from '../router';

export default {
  data() {
    return {
      name: "",
      email: "",
      username: "",
      password: ""
    };
  },

  methods: {
    register() {
      axios
        .post("http://localhost:1300/api/register", {
          name: this.name,
          username: this.username,
          email: this.email,
          password: this.password
        })
        .then(res => {
          console.log(res);
          router.push({ name: "Login" });
        })
        .catch(err => {
          console.log(err);
        });
    }
  }
};
</script>
