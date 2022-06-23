<template>
    <div class="box">
        <!-- This text will shown if the text in not passed in the component tag other than named slots -->
        <slot>This is the default text for the slot</slot>
        <slot name="links"></slot>
    </div>
</template>

<script>
    export default{
        name:"slotCustom"
    }
</script>


<style scoped>
    .box{
        border:2px solid blue;
    }
</style>