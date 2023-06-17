<script setup>
import { ref } from 'vue';

const posts = ref([]);

const api = async () => {
  const request = await fetch('https://jsonplaceholder.typicode.com/posts')
  const data = await request.json();
  posts.value = data;
}
api();
</script>

<template>
  <main class="bg-gray-300 p-12">
    <h1 class="text-center text-4xl mb-12 font-semibold underline">CARDS</h1>
  <section class=" grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-10 ">
        <div class="rounded-lg border-2 border-black hover:-translate-y-1 border-solid transition-transform bg-blue-900 font-semibold  text-white text-center hover:shadow-2xl" v-for="post in posts" :key="post.id">
          <h2 class=" border-b-2 bg-blue-700 border-gray-50 p-4">{{ post.title }}</h2>
          <h3 class="p-2">{{ post.body }}</h3>
          <h4>{{ post.id }}</h4>
      </div>
    </section>
  </main>
</template>

<style></style>