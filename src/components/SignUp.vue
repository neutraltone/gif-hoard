<template>
  <div class="login">
    <h3>Create a new account</h3>
    <div>
      <label for="email">Email Address</label>
      <input type="email" id="email" v-model="email" placeholder="joe@smith.com">
    </div>
    <div>
      <label for="password">Password</label>
      <input type="password" id="password" v-model="password" placeholder="Password">
    </div>
    <button v-on:click="signUp">Sign Up</button>
    <p><router-link to="/login">← Go Back</router-link></p>
  </div>
</template>

<script>
  import firebase from 'firebase';
  /* eslint-disable object-shorthand */
  /* eslint-disable func-names */
  /* eslint-disable no-unused-vars */
  export default {
    name: 'signUp',
    data: function () {
      return {
        email: '',
        password: '',
      };
    },
    methods: {
      signUp: function () {
        firebase.auth().createUserWithEmailAndPassword(this.email, this.password).then(
          (user) => {
            this.$router.replace('hello');
          },
          (err) => {
            alert(`Oops. ${err.message}`);
          },
        );
      },
    },
  };
</script>

<style scoped>

</style>
