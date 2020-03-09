<template>
  <div>
    <div>{{ msg }}</div>
    <br />
    <p>The button below uses the WP REST API to fetch this WP installation's users and output that info as an array of objects into the console (Shift + Ctrl + J)</p>
    <v-btn @click="fetchUsers()" color="success">Test Fetch users</v-btn>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",

  data() {
    return {
      msg: "Welcome Sam, to Your Vue.js Admin App.",
      url: admin.root,
      posts: "wp/v2/posts",
      users: "wp/v2/users"
    };
  },
  mounted() {
    console.log("data -> admin.root", admin.root + this.users);
  },
  methods: {
    // Make a request for a user with a given ID
    fetchUsers() {
      axios
        .get(admin.root + this.users, {
          params: {
            ID: 12345
          }
        })
        .then(function(response) {
          // handle success
          console.log(response.data);
        })
        .catch(function(error) {
          // handle error
          console.log(error);
        })
        .then(function() {
          // always executed
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
