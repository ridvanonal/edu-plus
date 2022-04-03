<template>
 <div class="container">
    <div class="card p-2 mt-3">
      <line-picker v-model="selected" label="text" decisive="id" :options="list" multiline></line-picker>
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
      list:[
        {id:1,text:"Muz"},
        {id:2,text:"Elma"},
        {id:3,text:"Çilek"},
        {id:4,text:"Kavun"},
        {id:5,text:"Karpuz"},
        {id:6,text:"Kivi"},
        {id:7,text:"Narenciye"},
        {id:8,text:"Narenciye"},
        {id:9,text:"Narenciye"},
        {id:10,text:"Narenciye"},
        {id:11,text:"Narenciye"},
      ]
    }
  },
  methods:{
    
  }
}
</script>

<style>

</style>
