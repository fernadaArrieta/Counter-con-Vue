
<template>
  <div>
    <h2>{{customTitle}}</h2>
    <p>{{counter}} <sup>2</sup>={{squareCounter}}</p>
    <div>
        <button v-on:click="increase()">+1</button>
        <button v-on:click="decrease()">-1</button>
    </div>
  </div>
</template>

<script>
export default {
props:
{
    title: String,
    start: {
        type: Number,
        default: 100
        //require: true
    }
},


data(){
    return{
        counter: this.start
    }
},
methods:{
    getSquareValue(){
        return this.counter * this.counter
    },
    increase(){
        this.counter++
    },
    decrease(){
        this.counter--
    }
},
computed:{
    squareCounter(){
        return this.counter* this.counter
    },
    customTitle(){
    return this.title || 'Counter'
    }
}
}
</script>

<style>

button{
    background-color: #64BB87;
    border-radius: 5px;
    color: white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;

};
button:hover{
    background-color: #407657;
    transition: 0.3s ease-in-out;
}

</style>
