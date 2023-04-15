<template>
  <div id="app">
    <h1>Would You Rather</h1>

    <would-you-rather v-for=" (question, index) in questions"
                      :key="index"
                      :question="question"
                      v-on:answer-changed="answerChanged" >
    </would-you-rather>

    <p>{{userSelectionMessage}}</p>
  </div>

</template>

<script>
import WouldYouRather from './components/WouldYouRathequiz.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
    questions: [
      {
        id:0,
        Question: 'be a detective or a pilot?',
        Answer1: 'be a pilot',
        Answer2: 'be a detective',
      },
      {
        id:1,
        Question:'would you rather dance or sing?',
        Answer1: 'I will sing',
        Answer2: 'I will dance',
      },
      {
       id:2,
       Question: 'would you rather be a superhero or wizard?',
       Answer1: 'Be a wizard',
       Answer2: 'Be a superhero',
      }
    ],
      userSelectionMessage:''
    }
  },

  methods: {
    answerChanged(choice) {
      this.userSelectionMessage = `Thanks! you chose ${choice}`

    }
  }
}
</script>

<style>

body {
  background: darkkhaki;
}
#app {
  font-family: Agency FB;

  text-align: center;
  color: aqua;
  margin-top: 70x;
  background: azure;
}
</style>
