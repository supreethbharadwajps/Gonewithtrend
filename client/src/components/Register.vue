<template>
  <div>
  <h1>Register Here</h1>
    <input type="email" v-model="email" placeholder="Enter Email" required>
    <br>
    <input type="password" v-model="password" placeholder="Enter Password" name="psw" required>
    <br>
    <button type="submit" @click="register">Sign ME UP </button>
    <br>
      <input type="checkbox" checked="checked" name="remember"> Remember me
     </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
  color: #42b983;
}
</style>
