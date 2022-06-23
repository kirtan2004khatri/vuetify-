<template>
    <div class="colorBox">
        <div class="box1">
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusantium, sed eius eum necessitatibus sint repudiandae numquam dolore quibusdam nam? Odit quo adipisci at ipsam harum.</p>
        </div>
        <div class="box2">
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut natus mollitia, voluptatem suscipit ullam accusantium repudiandae eligendi quis! Et, ad facere vero quaerat aliquid ea esse assumenda odio alias sequi nobis blanditiis distinctio corporis.</p>
        </div>
    </div>
</template>

<script>
    export default{
        name:'FirstCustom'  
    }
</script>

<style scoped>
    .box1{
        background-color: crimson;color:yellow
    }
    .box2{
        background-color: aqua;color:green;
    }
    .colorBox{
        width:500px;
        height:300px;
        display:flex;
    }
</style>
