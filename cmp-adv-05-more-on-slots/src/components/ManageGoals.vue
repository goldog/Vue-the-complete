<template>
  <div>
    <h2>Manage Goals</h2>
    <input type="text" ref="goal"/>
    <button @click="setGoal">Set goal</button>    
    <error-alert v-if="inputIsInvalid">
      <h2>입력이 이상해요</h2>
      <p>값을 제대로 입력하세요</p>
      <button @click="confirmError">확인</button>
    </error-alert>    
  </div>
</template>

<script>
import ErrorAlert from './ErrorAlert.vue';

export default {
  components: { 
    ErrorAlert, 

  },
  
  data() {
    return {
      inputIsInvalid: false,
    }
  },
  methods: {
    setGoal() {
      const enteredValue = this.$refs.goal.value;
      if (enteredValue === '') {
        this.inputIsInvalid = true;
      }
    },
    confirmError() {
      this.inputIsInvalid = false;
    }
  },
}
</script>