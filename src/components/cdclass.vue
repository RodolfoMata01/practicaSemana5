<template>
    <b-table striped hover :items="compoclass" :fields="fields"></b-table>
</template>

<script>

    import axios from 'axios'
    export default{
        name:'cdclass',
        data(){
            return{
                compoclass:[],
            }
        },
        created(){
        axios.get('https://api-crud-example.herokuapp.com/Department/read')
        .then(response=>{
            this.compoclass = response.data
            console.log(response.data)

        })
        .catch(e=>{
            this.error.push(e)
        })
    }
    }
    

</script>