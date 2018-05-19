<template>
  <div id="app">
    <!--<h1>Twój e-mail to {{ email.length }}</h1>.
    <h1>Twój e-mail to {{ email.toLowerCase() }}</h1>.
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <input type="email" v-model="email">  dyrektywy v model z vue 
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
    -->
    <h1>Witaj w systemi do zapisow na zajecia</h1>.
    <div v-if="zalogowany">
      <p>Witaj {{ email }} </p> 
      <button @click="logout()"> Wyloguj</button>        
    </div>
    <div v-else>
      <p>zaloguj sie emailem: </p>
      <input type="email" v-model="email"> 
      <button @click="LogIn()">Wchodze</button>
    </div>

  </div>
</template>

<script>
import "milligram";
export default {
  name: 'app',
  data () {
    return {
      email: 'amm3@wp.pl', // komponent ma jakis stan i na podstawi tego wyswietla go w templaciei
      zalogowany : false
    }
   },
   methods: {
      alertMyEmail() {
      alert(this.email);
      },
      LogIn(){
        this.zalogowany = true;
      },
      logout(){
        this.zalogowany = false;
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
