<script lang="ts" setup>
import { account } from '@/utils/appwrite'
import { useAuthStore, useIsLoadingStore } from '~/store/auth.store'

const isLoadingStore = useIsLoadingStore()
const store = useAuthStore()
const router = useRouter()

const logout = async() => {
    isLoadingStore.set(true)
    await account.deleteSession('current')
    store.clear()
    await router.push('/login ')
    isLoadingStore.set(false)
}
</script>

<template>
    <aside class="px-5 py-8 h-full relative w-full">
        <NuxtLink to="/" class="mb-10 block">
            <NuxtImg src="/logo.svg" alt="logo" class="mx-auto" />
        </NuxtLink>
        <button  @click="logout" class="absolute top-2 right-3 transition-colors hover:text-[#53b9ea]">
            <Icon name="line-md:logout" size="20" />
        </button>

        <LayoutMenu />
    </aside>
</template>

<style scoped>
    aside {
        background: linear-gradient(180deg, rgba(38, 34, 80, 0.65) 0%, rgba(27, 25, 66, 0.85) 57.44%, #17163b 100%);
    }
</style>
