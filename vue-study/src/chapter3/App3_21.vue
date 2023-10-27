<template>
  <Component>
    <template v-slot="slotProps"> v {{ slotProps.item }}</template>
  </Component>
</template>

<script>

import Component from 'vue';

export default {
  data(){
    return{
      items:[1,2,3]
    }
  }
}

</script>