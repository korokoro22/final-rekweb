<style scoped>
    .post__create {
        margin: 20px 10px;
    }

    form {
        display: flex;
        flex-direction: column;
        row-gap: 15px;
    }

    .inptext {
        width: 20%;
        height: 25px;
        font-size: 14px;
        padding: 3px;
    }

    .btn {
        width: 100px;
        height: 30px;
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
    <div class="post__create">
        <form @submit.prevent="form.put(`/post/update/${post.id}`)">
            <div>
                <label>Nama :</label><br>
                <input class="inptext" type="text" v-model="form.nama">
            </div>
            <div>
                <label>NIM :</label><br>
                <input class="inptext" type="text" v-model="form.nim">
            </div>
            <div>
                <label>Penerima KIP :</label><br>
                <input type="radio" id="html" name="fav_language" value="YA" v-model="form.kip">
                <label for="html">YA</label><br>
                <input type="radio" id="css" name="fav_language" value="TIDAK" v-model="form.kip">
                <label for="css">TIDAK</label>
            </div>
            <div>
                <input class="btn" type="submit" value="Perbarui data">
            </div>
        </form>
    </div>
</template>

<script setup>
    import { useForm } from '@inertiajs/vue3';
    import { defineProps } from 'vue';

    let props = defineProps({
        post: Object
    });

    const form = useForm({
        nama: props.post.nama,
        nim: props.post.nim,
        kip: props.post.kip
    });
</script>