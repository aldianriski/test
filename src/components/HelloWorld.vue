<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="login()">login</button>
    <button @click="logout()">logout</button>
    <button @click="post()">post</button>
    <button @click="get()">get</button>
    <button @click="put()">put</button>
    <button @click="del()">delete</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  created() {},
  methods: {
    login() {
      axios({
        method: "post",
        url: "http://localhost:8080/login",
        data: {
          username: "admin",
          password: "admin"
        }
      }).then(function(response) {
        console.log(response.data.data);
      });
    },
    logout() {
      axios({
        method: "post",
        headers: {
          Authorization:
            "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.e30.t-IDcSemACt8x4iTMCda8Yhe3iZaWbvV5XKSTbuAn0M"
        },
        url: "http://localhost:8080/logout"
      }).then(function(response) {
        console.log(response.data.data);
      });
    },
    post() {
      axios({
        method: "post",
        headers: {
          Authorization:
            "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.e30.t-IDcSemACt8x4iTMCda8Yhe3iZaWbvV5XKSTbuAn0M"
        },
        url: "http://localhost:8080/benefits",
        data: {
          title: {
            id: "Mengantarkan Dengan Dampak",
            eng: "Delivery The Impact"
          },
          description: {
            id: "Lorem Ipsum Dolor Sit Amet",
            eng: "Lorem Ipsum Dolor Sit Amet"
          },
          imagevideo: "Link",
          status: "Inactive"
        }
      }).then(function(response) {
        console.log(response.data.data);
      });
    },
    put() {
      axios({
        method: "put",
        headers: {
          Authorization:
            "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.e30.t-IDcSemACt8x4iTMCda8Yhe3iZaWbvV5XKSTbuAn0M"
        },
        url: "http://localhost:8080/benefits/5d4a46aa4a6493cc346b6c66",
        data: {
          title: {
            id: "Mengantarkan Dengan Dampak",
            eng: "Delivery The Impact"
          },
          description: {
            id: "Lorem Ipsum Dolor Sit Amet",
            eng: "Lorem Ipsum Dolor Sit Amet"
          },
          imagevideo: "Link",
          status: "Inactive"
        }
      }).then(function(response) {
        console.log(response.data.data);
      });
    },
    get() {
      axios({
        method: "get",
        headers: {
          Authorization:
            "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.e30.t-IDcSemACt8x4iTMCda8Yhe3iZaWbvV5XKSTbuAn0M"
        },
        url: "http://localhost:8080/benefits"
      }).then(function(response) {
        console.log(response.data.data);
      });
    },
    del() {
      axios({
        method: "delete",
        headers: {
          Authorization:
            "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.e30.t-IDcSemACt8x4iTMCda8Yhe3iZaWbvV5XKSTbuAn0M"
        },
        url: "http://localhost:8080/benefits/5d4a46aa4a6493cc346b6c66"
      }).then(function(response) {
        console.log(response.data.data);
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
  color: #42b983;
}
</style>
