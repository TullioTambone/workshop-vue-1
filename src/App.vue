<script >
export default{

  data(){
    return{
      pizzas:[],
      baseUrl: 'http://127.0.0.1:8000',
    }
  },
}
</script>

<template>
<RouterView></RouterView>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
