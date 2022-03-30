<template>
  <div class="row g-2">
    <div 
      class="col"
      :class="modelValue == emoji ? 'selected':''" 
      v-for="emoji in emojies" 
      :key="emoji" v-text="emoji"
      v-on:click="change(emoji)">
    </div>
  </div>
</template>

<script>
  export default {
    props:{
      modelValue:{
        type:String,
        default:null
      },
      emojies:{
        type:Array,
        default: () => []
      }
    },
    data(){
      return{
        selected: this.modelValue !== undefined ? this.modelValue : null,
      }
    },
    methods:{
      change(emoji){
        this.selected = emoji
        this.$emit('update:modelValue',emoji)
        this.$emit('change',emoji)
      }
    }

  }
</script>

<style>

</style>