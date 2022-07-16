<template>
  <div class="form-signin">
    <form>
      <h1 class="h3 mb-3 fw-normal text-center">Please sign in</h1>

      <div class="form-floating">
        <input
          type="email"
          class="form-control"
          placeholder="name@example.com"
        />
        <label>Email address</label>
      </div>
      <div class="form-floating">
        <input type="password" class="form-control" placeholder="Password" />
        <label>Password</label>
      </div>
      <button class="w-100 btn btn-lg btn-primary" type="submit">
        Sign in
      </button>
    </form>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Login',
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
