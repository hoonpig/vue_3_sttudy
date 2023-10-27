<template>
  <MyButton sm>My button</MyButton>
  <MyButton>My button</MyButton>
  <MyButton lg background-white>My button</MyButton>
  <MyButton sm pill text-red background-black>My button</MyButton>
  <MyButton md pill text-green background-pink>My button</MyButton>
  <MyButton lg pill @click.prevnet="onClick">My button</MyButton>

</template>

<script>

import MyButton from './App3_30.vue';

export default{
  name : 'App'
  , methods:{
    onClick(evt){
      alert('clicked');
    }
  }
  , components : {
      MyButton
  }
}

</script>
