<template>
  <h2>{{ customTitle}}!!!</h2>
  <p> {{counter}} <sup> 2</sup> = {{squareCounter}} </p>
  
  
  <button @click="increase"> +1 </button>
  <button @click="decrease"> -1 </button>

</template>
<script>
export default {
  props:{
    title:String,
    start:{
      type:Number,
      default:100,
      validator(value){
        return value >= 0
      }
    }
  },

  data(){
    return{
      counter:this.start
    }
  },
  methods:{
    getSquareValue(){
      console.log('getSquareValue')
      return this.counter
    },
    increase(){
      return this.counter++
    },
    decrease(){
      return this.counter--
    }
  },
  computed:{
    squareCounter(){
      console.log('squareCounter')
      return this.counter * this.counter
    },
    customTitle(){
      return this.title || 'Counter'
    }
  }
}
</script>

<style>
  button{
    background-color: #64B687;
    border-radius: 1px solid white;
    color:white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
  }
</style>
