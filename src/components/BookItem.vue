<template>
    <li>{{book.title}}:{{book.author}}</li>
</template>
<script>
export default {
    name: 'BookItem',    
    props: ['book'],
    data: function() {
    }
};
</script>
<style>
    li {        
        display: block;
        margin: 0 10px;
    }
</style>


