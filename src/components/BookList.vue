<template>
  <div class="bg-white">
    <div class="mx-auto max-w-7xl py-24 sm:px-6 sm:py-32 lg:px-8">
      <div
        class="relative isolate overflow-hidden bg-gray-900 px-6 pt-16 shadow-2xl sm:rounded-3xl sm:px-16 md:pt-24 lg:flex lg:gap-x-20 lg:px-24 lg:pt-0"
      >
        <svg
          viewBox="0 0 1024 1024"
          class="absolute left-1/2 top-1/2 -z-10 h-[64rem] w-[64rem] -translate-y-1/2 [mask-image:radial-gradient(closest-side,white,transparent)] sm:left-full sm:-ml-80 lg:left-1/2 lg:ml-0 lg:-translate-x-1/2 lg:translate-y-0"
          aria-hidden="true"
        >
          <circle
            cx="512"
            cy="512"
            r="512"
            fill="url(#759c1415-0410-454c-8f7c-9a820de03641)"
            fill-opacity="0.7"
          />
          <defs>
            <radialGradient id="759c1415-0410-454c-8f7c-9a820de03641">
              <stop stop-color="#7775D6" />
              <stop offset="1" stop-color="#E935C1" />
            </radialGradient>
          </defs>
        </svg>
        <div class="mx-auto max-w-md text-center lg:mx-0 lg:flex-auto lg:py-32 lg:text-left">
          <h2 class="text-1xl font-bold tracking-tight text-white sm:text-4xl">
            Livre en cours<br /><span class="text-2xl text-amber-500">{{ book.name }}</span>
          </h2>
          <p class="mt-6 text-lg leading-8 text-gray-300">
            {{ book.description }}
          </p>
          <div class="mt-10 flex items-center justify-center gap-x-6 lg:justify-start">
            <a
              @click="readPages"
              href="#!"
              class="rounded-md bg-white px-3.5 py-2.5 text-sm font-semibold text-gray-900 shadow-sm hover:bg-gray-100 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-white"
              >Lire des pages</a
            >
            <a href="#" class="text-sm font-semibold leading-6 text-white"
              >Vous avez lu <span aria-hidden="true">→ {{ book.pagesRead }}</span></a
            >
          </div>
        </div>
        <div class="relative mt-16 h-80 lg:mt-8">
          <img
            class="absolute left-0 top-0 w-[57rem] max-w-none rounded-md bg-white/5 ring-1 ring-white/10"
            src="https://images.unsplash.com/photo-1663613719625-23904359858f?q=80&w=2005&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            alt="App screenshot"
            width="1824"
            height="1080"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed, ref, watchEffect } from 'vue'

const book = ref({
  name: 'La porte des Enfers',
  author: 'Laurent Gaudé',
  description:
    "Au lendemain d'une fusillade à Naples, Matteo voit s'effondrer toute raison d'être. Son petit garçon est mort. Sa femme, Giuliana, disparaît. Lui-même s'enfonce dans la solitude et, nuit après nuit, à bord de son taxi vide, parcourt sans raison les rues de la ville.",
  pagesCount: 268,
  pagesRead: 0
})

const evenPagesRead = computed((): boolean => book.value.pagesRead % 2 === 0)

const readPages = () => (book.value.pagesRead = Math.ceil(Math.random() * 268))

watchEffect(() => console.log(`Nombre de pages paires lues : ${evenPagesRead.value}`))
</script>
