<template>
  <ul style ="list-style-type:none">
    <li v-for="item in items">
      <slot :item="item"></slot>
    </li>
  </ul>
</template>

<script>

import {reactive, ref} from 'vue';

export default {
  data(){
    return{
      items:[1,2,3]
    }
  }
}

</script>