<template>
    <div class="container">

        <table class="table mt-5">
            <thead>
            <tr>
                <th scope="col">#</th>
                <th scope="col">post</th>
                <th scope="col">body</th>
            </tr>
            </thead>
            <tbody>
            <tr if v-for="post in posts" :key="post.id">
                <th scope="row">{{post.id}}</th>
                <td>{{post.title}}</td>
                <td>{{post.body}}</td>
            </tr>

            </tbody>
        </table>
        <button class="btn btn-primary">click</button>

    </div>
</template>


<script>
import axios from "axios";

    export default {
        name: 'postExample',
        data() {
            return {
                posts: [

                ]
            }
        },

        created(){
            axios.get('https://jsonplaceholder.typicode.com/posts').then(post =>{

                this.posts = post.data;
            })
        }
    }

</script>


<style>


</style>