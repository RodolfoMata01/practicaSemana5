<template>

    <b-table striped hover :items="employees" :fields="fields"></b-table>
    
</template>
B
<script>
import axios from 'axios'

export default{
    name:'Employee',
    data(){
        return{
            employees:[],


        }
    },
    created(){
        axios.get('https://api-crud-example.herokuapp.com/Employee/read')
        .then(response=>{
            this.employees = response.data
            console.log(response.data)
        })
        .catch(e=>{
            this.erorrs.push(e)
        })


    }


}

</script>
