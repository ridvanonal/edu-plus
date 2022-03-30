<template>
 <div class="container">
    <div class="card p-2">
      <line-picker v-model="emoji" label="emoji" decisive="id" :options="emojies">
        <template v-slot:option="{option:option}">
          {{option.emoji}}
        </template>
      </line-picker>
      <line-picker class="mt-2" v-model="emoji" label="emoji" decisive="id" :options="emojies">
      </line-picker>

      <line-picker class="mt-2" v-model="selected" label="text" decisive="id" :options="choose">
      </line-picker>
   </div>
   
 </div>
</template>

<script>
import LinePicker from './components/LinePicker.vue'

export default {
  name: 'App',
  components: {
    LinePicker
  },
  data(){
    return{
      emojies:[{id:1,emoji:'😟'},{id:2,emoji:'🙁'},{id:3,emoji:'🙂'},{id:4,emoji:'😊'},{id:5,emoji:'🥳'}],
      emoji:{id:2,emoji:'🙁'},
      selected:null,
      choose:[{id:1,text:"Yes"},{id:2,text:"No"}]
    }
  },
  methods:{
   
  }
}
</script>

<style>
  .card{
    margin: 20px;
    background-color: rgb(var(--color-white));
    border-radius: 0.75rem;
    box-shadow: 0px 2px 10px -7px rgb(var(--color-gray-2));
  }
</style>
