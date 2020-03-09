<template>
  <div class="home">
    <span>{{ msg }}</span>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",

  data() {
    return {
      msg: "Welcome Dylan, to Your Vue.js Admin App",
      url: admin.root,
      posts: "wp/v2/posts",
      users: "wp/v2/users"
    };
  },
  mounted() {
    console.log("data -> admin.root", admin.root + this.users);

    // Make a request for a user with a given ID
    axios
      .get(admin.root + this.users, {
        params: {
          ID: 12345
        }
      })
      .then(function(response) {
        // handle success
        console.log(response);
      })
      .catch(function(error) {
        // handle error
        console.log(error);
      })
      .then(function() {
        // always executed
      });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
