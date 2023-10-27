<template>
  <div id="date">
    {{ date }}
  </div>
  <div id="date2">
    {{ date2 }}
  </div>
  <p v-text="date"></p>
  <p v-pre>{{ date2 }}</p>
</template>

<script>
  export default {
    setup(){
      const date = Date().toString();
      return {
        date:Date().toString()
      }
    },

    data(){
      return {
        date2:Date().toString()
      }
    }
}
</script>