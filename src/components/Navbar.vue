<script setup>
import logo from '@/assets/img/logo.png'
import { RouterLink, useRoute } from 'vue-router';

const isActiveLink = (routePath) => {
  const route = useRoute();
  return route.path === routePath;
}
</script>

<template>
    <nav class="bg-purple-700 border-b border-purple-500">
      <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
        <div class="flex h-20 items-center justify-between">
          <div
            class="flex flex-1 items-center justify-center md:items-stretch md:justify-start"
          >
            <!-- Logo -->
            <RouterLink class="flex flex-shrink-0 items-center mr-4" to="/">
              <img class="h-10 w-auto" :src="logo" alt="Vue Jobs" />
              <span class="hidden md:block text-white text-2xl font-bold ml-2"
                >Look for Jobs</span
              >
            </RouterLink>
            <div class="md:ml-auto">
              <div class="flex space-x-2">
                <RouterLink
                  to="/"
                  :class="[isActiveLink('/') ? 'bg-purple-900' : 'hover:bg-purple-500 hover:bg-text-white', 'text-white', 'px-3', 'py-2', 'rounded-md']">
                  Home
                </RouterLink>
                <RouterLink
                  to="/jobs"
                  :class="[isActiveLink('/jobs') ? 'bg-purple-900' : 'hover:bg-purple-500 hover:bg-text-white', 'text-white', 'px-3', 'py-2', 'rounded-md']">
                  Jobs</RouterLink
                >
                <RouterLink
                  to="/jobs/add"
                  :class="[isActiveLink('/jobs/add') ? 'bg-purple-900' : 'hover:bg-purple-500 hover:bg-text-white', 'text-white', 'px-3', 'py-2', 'rounded-md']">
                  Add Job</RouterLink
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>

</template>