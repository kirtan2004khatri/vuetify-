<template>
    <div class="modal-bg">
        <div class="modal" :class="{change:condition==='change'}">
            <h1>{{modalTitle}}</h1>
            <p>{{modalContent}}</p>
            <button @Click="closeEvent">Close</button><br>
            <button @Click="color">Change Color</button> 
        </div>
    </div>
</template>

<script>
    export default{
        name:"MyModal",
        props:{
            modalTitle:String,
            modalContent:String,
            condition:String
        },
        methods:{
            closeEvent(){
                // Here the $emit is used to emit and custom event
                this.$emit('close');
            },
            color(){
                this.$emit('changeColor');
            }
        }
    }
</script>

<style scoped>
    .modal-bg{
        width:100vw;
        height:100vh;
        background-color: rgb(0,0,0,0.5);
        position:fixed;top:0;left:0;
        display:flex;justify-content: center;align-items:center;
    }
    .modal{
        background-color:white;
        height:300px;width:500px;
        padding:15px;border-radius:12px;
    }
    button{
        display:block;margin:auto;
    }
    .change{
        background-color: black;color:white;
    }
</style>