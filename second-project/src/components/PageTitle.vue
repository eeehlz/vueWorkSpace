<template>
  <h2>{{ title }}</h2>
</template>
<script>
  export default {
    /*data(){
      return {
        title : 'Hello, World!',
      }
    }*/
    //부모가 넘겨준 값 : props
    props: ['title'],
    created() {
      console.log('App.vue Created');
    },
    mounted() {
      console.log('App.vue Mounted');
    },
  }
</script>