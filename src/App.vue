<template>
 <div class="container">
   <emoji-picker v-model="emoji" :emojies="['😟','🙁','🙂','😊','🥳']"></emoji-picker>
   {{emoji}}
 </div>
</template>

<script>
import EmojiPicker from './components/EmojiPicker.vue'


export default {
  name: 'App',
  components: {
    EmojiPicker
  },
  data(){
    return{
      emoji:"😟"
    }
  },
  methods:{
   
  }
}
</script>

<style>

</style>
