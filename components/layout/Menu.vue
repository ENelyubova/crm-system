<script lang="ts" setup>
import { MENU_DATA } from './menu.data'
</script>

<template>
    <div>
        <NuxtLink 
            v-for="item in MENU_DATA"
            :key="item.name"
            :to="item.url"
            active-class="text-[#53b9ea]"
            class="flex items-center py-1 px-1 rounded-lg w-full text-[#6f6c99] hover:text-[#53b9ea] transition-all mb-2.5"
        >
            <Icon :name="item.icon" class="mr-3" />
            <span>{{ item.name }}</span>
        </NuxtLink>
    </div>
</template>