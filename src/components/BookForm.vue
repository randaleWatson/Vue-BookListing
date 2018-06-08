<template>
    <form @submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
        <input type="text" name="title" v-model="bookTitle" placeholder="Book Title">
        <input type="text" name="author" v-model="bookAuthor" placeholder="Book Author">
        <button type="submit" name="button">Add Book</button>
    </form>
</template>
<script>
export default {
    name: 'BookForm',
    props: ['books'],
    data: function(){
        return {
            bookTitle: '',
            bookAuthor: ''
        }
    },
    methods: {
        bookSubmit: function(bookTitle, bookAuthor){
            this.$emit('addBook', bookTitle, bookAuthor);
        }
    }
};
</script>
<style>

</style>

