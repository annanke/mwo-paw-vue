<template>
  <div id="app">

    <h1>Witaj w systemi do zapisow na zajecia</h1>.
    <div v-if="!authenticatedEmail">
      <login-form @login="logMeIn($event)" :button-label="'Wejdź'"></login-form>
      <login-form @login="logMeIn($event)" :button-label="'zaloguj'"></login-form>
    </div>
    <div v-else>
      <p>Witaj {{ authenticatedEmail }} </p> 
      <button @click="logout()"> Wyloguj</button>      
    </div>

  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
  components: {LoginForm},
  name: 'app',
  data () {
    return {

      authenticatedEmail : ''
    }
   },
   methods: {

      logout(){
        this.authenticatedEmail = '';
      },
      logMeIn(email) {
          this.authenticatedEmail = email;
          
      }
  }

}


</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

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
