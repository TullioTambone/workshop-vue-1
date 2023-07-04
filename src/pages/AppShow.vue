<script>
import axios from 'axios';
export default{

    data(){
        return{
            pizza: [],
            baseUrl: 'http://127.0.0.1:8000',
        }
    },
    created(){
        this.getSinglePizza();
    },
    methods:{
        getSinglePizza(){
            axios.get(`${this.baseUrl}/api/pizza/${this.$route.params.id}`).then(res=>{
                
                this.pizza = res.data.pizza;
            })
        }
    }
}
</script>

<template>
<h1>{{ pizza.name }}</h1>
</template>

<style lang="scss" scoped>
</style>