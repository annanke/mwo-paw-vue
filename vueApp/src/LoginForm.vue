<template>
   <div>
       <label>Zaloguj się e-mailem</label>
       <input type="email" v-model="email">
       <button @click="enter()">{{buttonLabel}}</button>
   </div>
</template>

<script>
export default {
     props: ['buttonLabel'], //te infor moze dostac od komponentu zew - rodzica - towarcie na swiat

 data() {
     return {
         email: '' // na ten stan rodzic ne imoze wplywac
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 }
 }
</script>