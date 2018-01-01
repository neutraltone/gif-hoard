<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button v-on:click="logout">Logout</button>
  </div>
</template>

<script>
  import firebase from 'firebase';
  /* eslint-disable object-shorthand */
  /* eslint-disable func-names */
  /* eslint-disable no-unused-vars */
  export default {
    name: 'hello',
    data() {
      return {
        msg: `Welcome ${firebase.auth().currentUser.email}, feel free to logout.`,
      };
    },
    methods: {
      logout: function () {
        firebase.auth().signOut().then(() => {
          this.$router.replace('login');
        });
      },
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #35495E;
}
</style>
