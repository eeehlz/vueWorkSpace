<template>
  <!--Header Component-->
  <DefaultHeader></DefaultHeader>
  <router-view/>
  <!--footer Component-->
</template>
<script>
  import DefaultHeader from '@/layouts/DefaultHeader.vue'

  export default{
    components : {
      DefaultHeader,
    }
  }
</script>