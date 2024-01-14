<script setup lang="ts">
import { ref } from 'vue'
import BookList from './components/BookList.vue'
import NewsletterSection from './components/NewsletterSection.vue'
import UserAccount from './components/UserAccount.vue'

const email = ref<string>('')
const name = ref<string>('Ludovic')

const firstname = ref<string>('Luke');
const age = ref<number>(15);
</script>

<template>
  <main class="container mx-auto p-10">
    <!-- WatchEffect improvement -->
<!--     <BookList />-->

    <!-- defineModel is Now Stable -->
<!--    <NewsletterSection v-model:email="email" v-model:name="name" />-->

<!--    <div class="mt-10 mx-auto font-bold tracking-tight text-gray-900 lg:col-span-7">-->
<!--      <p class="text-2xl inline sm:block lg:inline xl:block">-->
<!--        {{ name }} participe à la Newsletter avec l'email suivant :-->
<!--        <span class="text-indigo-500">{{ email }}</span>-->
<!--      </p>-->
<!--    </div>-->

    <!-- shorthands -->
    <UserAccount :firstname :age />

  </main>
</template>
