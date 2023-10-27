<template>
  <p> {{  count_o }}</p>
  <button @click="count_o++">Options API 카운트 증가</button>

  <p> {{  count_c_1 }}</p>
  <button @click="count_c_1++">Composition API 1st 카운트 증가</button>

  <p> {{  count_c_2 }}</p>
  <button @click="count_c_2++">Composition API 1st 카운트 증가</button>

  <p>상태 : {{ state }}</p>
  <button @click="onStop()">watchEffect 중지</button>
</template>
<script>

import {ref, watch, watchEffect} from 'vue';

export default {
  // Options Api
  data(){
    return{
      count_o : 0,
    }
  },
  watch:{
    count_o:(cur, prev) =>{
      console.log('Options Api watch : ' + prev + ' ==> ' + cur);
    },
  },
  //Composition API
  setup(){
    const count_c_1 = ref(0);
    const count_c_2 = ref(0);
    const state = ref('실행중');

    watch(count_c_1, (cur, prev) =>{
      console.log('Composition Api watch : ' + prev + ' ==> ' + cur);
    },{
      immediate : true,
    })

    watch([count_c_1, count_c_2] , (cur, prev)=>{
      console.log('Composition Api Multiple watch : ' + prev + ' ==> ' + cur);
    })

    const stop = watchEffect(() => {
      console.log('Composition Api WatchEffect Called : ' + count_c_2.value);
    },{
      flush : 'post'
    })

    const onStop = ()=>{
      state.value = '중지';
      stop()
    }

    return {
      count_c_1
      , count_c_2
      , state
      , onStop
    }
  }
}



</script>