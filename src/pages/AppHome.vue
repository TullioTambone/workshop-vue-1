<script >
import axios  from 'axios';
export default{
    name:'AppHome',
  data(){
    return{
      pizzas:[],
      baseUrl: 'http://127.0.0.1:8000',
    }
  },
  mounted(){
    this.getPizza()
  },
  methods:{
    getPizza(){
      axios.get(`${this.baseUrl}/api/pizza`)
      .then(res => {
        this.pizzas = res.data.pizza
      })
    }
  }
}
</script>

<template>
  <div class="container">
    <div v-for="(e, i) in pizzas" :key="i">
      <RouterLink :to="{name: 'show', params:{id:e.id}}">
        {{ e.name }}
      </RouterLink>
    </div>
  </div>
</template>

<style lang="scss">
@use '../style/main.scss';
</style>
