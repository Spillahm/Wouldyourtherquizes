<template>
  <div>

    <h2>{{question.Question}}</h2>


    <div>

    <input type="radio" :id="question.id + '-answer1'" :value="question.Answer1" v-model="selectedAnswer">
    <label :for="question.id + '-answer1'">{{question.Answer1}}</label>
    </div>

    <div>
    <input type="radio" :id="question.id + '-answer2' " :value="question.Answer2" v-model="selectedAnswer">
    <label :for="question.id + '-answer2'">{{question.Answer2}}</label>
    </div>



  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: {
      type: Object,
      required: true
    }

  },
  data() {
    return {
      selectedAnswer: ''
    }
  },
  watch: {
    selectedAnswer(newValue){
      this.$emit('answer-changed', newValue)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2 {
  margin: 40px 0 0;
}

.id1 {
  border: 2x aqua;
  font-family: Avenir;
  background: aquamarine;
  margin: 15px;



}
#data {
  background-color: blue;
}
</style>
