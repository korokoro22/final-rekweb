<style scoped>
    nav {
        margin: 20px 0;
    }

    table {
        border-collapse: collapse;
        width: 80%;
    }

    th, tr, td {
        border: 1px solid black;
        padding: 8px;   
    }

    .btn {
        padding: 3px;
        background-color: rgb(186, 184, 184);
        border: 1px solid gray;
        text-decoration: none;
        color: black;
        border-radius: 5px;
    }

    .btn:hover {
        background-color: rgb(138, 138, 138);
    }
</style>

<template>
    <div class="container">
        <nav>
            <Link class="btn" href="/post/create">Tambah Data</Link>
        </nav>
        <table>
            <tr>
                <th>Nama</th>
                <th>NIM</th>
                <th>Penerima KIP</th>
                <th>Aksi</th>
            </tr>
            <tr v-for="post in posts" :key="post.id">
                <td>{{ post.nama }}</td>
                <td>{{ post.nim }}</td>
                <td>{{ post.kip }}</td>
                <td><Link :href="`/post/edit/${post.id}`" class="btn">Edit</Link>  |  
                    <Link :href="`/post/delete/${post.id}`" method="DELETE" class="btn">Hapus</Link>
                </td>
            </tr>
        </table>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';
import { Link } from '@inertiajs/vue3';

defineProps({
    posts: Object
})
</script>