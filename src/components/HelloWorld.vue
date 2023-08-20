<script>
export default {
  props: ['msg'],
  data(){
    return {
      timerId: -1,
      currentTextIndex: 0,
      text: '',
      greetingText:[
        'You’ve successfully created a project with1',
        'You’ve successfully created a project with2',
        'You’ve successfully created a project with3',
        'You’ve successfully created a project with4',
        'You’ve successfully created a project with5',
      ],
    }
  },
  mounted(){
    this.text = this.greetingText[0];
    this.timerId = setTimeout(this.changeText, 3000);
  },
  unmounted(){
    clearTimeout(this.timerId);
  },
  methods:{
    changeText(){
      clearTimeout(this.timerId);
      this.currentTextIndex++;
      if(this.currentTextIndex == this.greetingText.length) this.currentTextIndex = 0;  
      this.text = this.greetingText[this.currentTextIndex];
      this.timerId = setTimeout(this.changeText, 3000);
    }
  }
}
</script>

<template>
  <div class="greetings">
    <h1 class="green" @click="changeText">{{ msg }}</h1>
    <h3>
      {{ timerId }}
      {{ text }}
    </h3>
  </div>
</template>