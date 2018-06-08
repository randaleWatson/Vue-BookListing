<template>
    <div>
        <h1>{{title}}</h1>
        <ul>
            <book-item :book="book" :key="book.title" v-for="book in books">
                {{book.title}}:{{book.author}}
            </book-item>
        </ul>
        <book-form @addBook="appendBook"/>
    </div>
</template>
<script>
    import BookItem from './BookItem';
    import BookForm from './BookForm';
    export default {
        name: "BookList",
        components: {
            BookItem,
            BookForm
        },
        data: function(){
            return {
                title: 'All Books',
                books: [
                    {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
                    {title: 'American Gods', author: 'Neil Gaiman'},
                    {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
                ]
            }
        },
        methods: {
            appendBook: function(bookTitle, bookAuthor) {
                this.books.push({title: bookTitle, author: bookAuthor});
            }
        }
    };
</script>
<style>
    h1, h2 {
        font-weight: normal;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
</style>

