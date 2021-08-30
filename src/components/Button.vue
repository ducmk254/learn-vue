<template>
    <button @click="onClick()">{{name}}</button>
</template>
<script>
export default {
    name:'Button',
    props:{name:{type:String,default:"button"}},
    methods:{
        onClick(){
            console.log('click');
        }
    }
}
</script>

<style scoped>
button{
    padding: 10px 20px;
    background-color: rgb(12, 231, 231);
    color: white;
    outline: none;
    cursor: pointer;
    border: none;
    text-transform: capitalize;
}
</style>