<template>
  <div class="form-signin">
    <form @submit.prevent="submit">
      <h1 class="h3 mb-3 fw-normal text-center">Please Register</h1>

      <div class="form-floating">
        <input
          v-model="firstName"
          type="text"
          class="form-control"
          placeholder="First Name"
        />
        <label>First Name</label>
      </div>

      <div class="form-floating">
        <input
          v-model="lastName"
          type="text"
          class="form-control"
          placeholder="Last Name"
        />
        <label>Last Name</label>
      </div>

      <div class="form-floating">
        <input
          type="email"
          v-model="email"
          class="form-control"
          placeholder="Email"
        />
        <label>Email address</label>
      </div>

      <div class="form-floating">
        <input
          v-model="password"
          type="password"
          class="form-control"
          placeholder="Password"
        />
        <label>Password</label>
      </div>

      <div class="form-floating">
        <input
          type="password"
          v-model="password_confirm"
          class="form-control"
          placeholder="Confirm Password"
        />
        <label>Confirm Password</label>
      </div>
      <button class="w-100 btn btn-lg btn-primary" type="submit">Subit</button>
    </form>
  </div>
</template>

<script lang="ts">
import axios from 'axios';

export default {
  name: 'Register',
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      password: '',
      password_confirm: '',
    };
  },
  methods: {
    async submit() {

      const userObject = {
        firstName: this.firstName,
        lastName: this.lastName,
        email: this.email,
        password: this.password,
        password_confirm: this.password_confirm,
      }

      await axios.post('http://localhost:8000/api/admin/register', userObject);

      await this.$router.push('/login');
    },
  },
};
</script>

<style>
.form-signin {
  width: 100%;
  max-width: 330px;
  padding: 15px;
  margin: auto;
}

.form-signin .checkbox {
  font-weight: 400;
}

.form-signin .form-floating:focus-within {
  z-index: 2;
}

.form-signin input[type='email'] {
  margin-bottom: -1px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}

.form-signin input[type='password'] {
  margin-bottom: 10px;
  border-top-left-radius: 0;
  border-top-right-radius: 0;
}
</style>
