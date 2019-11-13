<template>
  <div id="app">
    <Page v-bind:notes="notes" />
  </div>
</template>

<script>
import Page from "./components/Page.vue";

export default {
  name: "app",
  components: {
    Page
  },
  data () {
    return {
      notes : [{
        avatar: "https://i.imgur.com/1o1zEDM.png",
        name: "Sajid Latif",
        daysago: 7,
        note: "Borger har det ikke så godt idag PGA. PåbegyndeneBorger har det ikke så godt idag PGA. Påbegyndene Borger har det ikke så godt idag PGA. Påbegyndene Borger har det ikke så godt idag PGA. Påbegyndene",
        comments: [{
          avatar: "https://i.imgur.com/cVDadwb.png",
          name: "Annette Lerche",
          daysago: 6,
          comment: "Borger har det ikke så godt idag PGA. Påbegyndene"
        },
        {
          avatar: "https://i.imgur.com/Yfbd3iA.png",
          name: "Annette Lerche",
          daysago: 2,
          comment: "Borger har det ikke så godt idag PGA. Påbegyndene"
        }]
      },
      {
        avatar: "https://i.imgur.com/1o1zEDM.png",
        name: "Sajid Latif",
        daysago: 7,
        note: "Borger har det ikke så godt idag PGA. PåbegyndeneBorger har det ikke så godt idag PGA. Påbegyndene Borger har det ikke så godt idag PGA. Påbegyndene Borger har det ikke så godt idag PGA. Påbegyndene",
        comments: [{
          avatar: "https://i.imgur.com/cVDadwb.png",
          name: "Annette Lerche",
          daysago: 6,
          comment: "Borger har det ikke så godt idag PGA. Påbegyndene"
        }]
      },
      {
        avatar: "https://i.imgur.com/1o1zEDM.png",
        name: "Sajid Latif",
        daysago: 7,
        note: "Borger har det ikke så godt idag PGA. PåbegyndeneBorger har det ikke så godt idag PGA. Påbegyndene Borger har det ikke så godt idag PGA. Påbegyndene Borger har det ikke så godt idag PGA. Påbegyndene",
        comments: []
      }]
    }
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
