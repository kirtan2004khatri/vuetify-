<template>
    <div class="propCont" :class="{addClass:condition ==='red',greenClass:condition==='green'}" @click="greenColor">
        <h1>This is the prop data : {{propData}}</h1>
        <p>This is the condition : {{condition}}</p>
    </div>
</template>

<script>
    export default{
        name:"propCustom",
        // Passing props in this way is recommanded with the data type
        props:{
            propData:String,
            condition:String
        },
        // props:[propData,condition] you can also pass the props like this in array
        methods:{
            greenColor(){
                this.$emit('green')
            }
        }
    }
</script>

<style scoped>
    .addClass{
        background-color: red;color:white;
    }
    .greenClass{
        background-color: green;color:yellow;
    }
</style>