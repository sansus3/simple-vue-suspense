<template>
  <main>
    <header>
      <h1 class="text-center text-4xl">Suspense</h1>
    </header>
    <div class="mt-10">
      <Suspense>
        <!-- Componente/contenido a cargar cuando se cumpla la promesa -->
        <UserComponent></UserComponent><!-- Componente/contenido End -->
        <!-- fallback - Segunda parte del suspense -->
        <template #fallback>
          <div
            class="w-full max-w-sm bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700 p-5 m-auto">
            <div class="animate-pulse flex flex-col items-center">
              <div class="mb-3 rounded-full w-24 h-24 bg-slate-200"></div>
              <div class="grid grid-cols-12 gap-4">
                <div class="mb-1 h-3 bg-slate-200 rounded col-span-12"></div>
                <div class="mb-1 h-2 bg-slate-200 rounded col-span-12"></div>
              </div>
            </div>
          </div>
        </template><!-- fallback End -->
      </Suspense>
    </div>

  </main>
</template>
<script setup>
import UserComponent from './components/UserComponent.vue';
</script>