<script>
//import axios from 'axios'; //questa la sta importando de la libreria che ho scaricato di axios e messo nell header

export default {
  name: 'App',
  data() {
    return {
      Emails: []
    }
  },

  mounted() {
    for (let index = 0; index < 10; index++) {
      axios
        .get('https://flynn.boolean.careers/exercises/api/random/mail')
        .then((response) => {
          console.log(response);
          console.log(this);
          this.Emails.push(response.data.response);

        })
    }
  }
}
</script>

<template>
  <h3>Lista Emails:</h3>
  <ul v-for="email in Emails">
    <li>{{ email }}</li>
  </ul>
</template>

<style></style>
