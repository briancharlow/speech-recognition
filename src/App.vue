<script setup>
import {ref, onMounted} from 'vue';

const transcript = ref('')
const isRecording= ref(false);

const Recognition = window.SpeechRecognition || window.webkitSpeechRecognition;
const sr = new Recognition();

onMounted(()=>{
  sr.continuous = true;
  sr.interimResults= true;

  sr.onstart = ()=>{
    console.log('SR has started')
    isRecording.value=true;

  }
})

</script>

<template>
  <div>
      <button class="`mic`">Recording</button>
      <div class="transcript"></div>
 </div>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  background: rgb(55, 44, 57);
  color: #fff;
}
</style>
