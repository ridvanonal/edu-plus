<template>
  <div class="line-picker row g-2 user-select-none" :class="[disabled ? 'disabled':'']">
    <div :class="multiline ? 'col-auto' : 'col'" class="line-wrapper" v-for="option in options" :key="option[decisive]" v-on:click="change(option)">
      <div class="text-center option px-2 py-1" :class="modelValue != null && modelValue[decisive] == option[decisive] ? 'selected':''" >
        <slot v-if="$slots.option" name="option" :option="option"></slot>
        <span v-else>{{label ? option[label] : option}}</span>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props:{
      disabled:Boolean,
      multiline:Boolean,
      multiple:Boolean,
      modelValue:{
        default:null
      },
      options:{
        type:Array,
        default: () => []
      },
      label:{
        type:String,
      },
      decisive:{
        type:String,
        required:true
      },
    },
    data(){
      return{
        selected: this.modelValue !== undefined ? this.modelValue : null,
      }
    },
    methods:{
      change(option){
        if(!this.disabled){
          this.selected = option
          this.$emit('update:modelValue',option)
          this.$emit('change',option)
        }
      }
    }

  }
</script>

<style scoped>
  .line-picker.multiline > div.line-wrapper:not(:last-child){
    margin-right: 0.5rem;
  }
  .line-picker > div.line-wrapper > div.option{
    border-radius: 0.5rem;
    border: 1px solid transparent;
    cursor: pointer;
    background-color: rgb(var(--color-gray-6));
    font-size: 0.85em;
    color: rgb(var(--color-black),0.7);
  }
  .line-picker > div.line-wrapper > div.option.selected{
    border-color:rgb(var(--color-blue));
    background-color: rgb(var(--color-blue),0.1);
    color: rgb(var(--color-blue));
  }
  .line-picker.disabled > div.line-wrapper > div.option.selected{
    border-color:rgb(var(--color-gray-3));
  }
  .line-picker.disabled > div.line-wrapper > div.option{
    filter: grayscale(100%)
  }
</style>