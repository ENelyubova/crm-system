<script setup lang="ts">
import { useDealSlideStore } from '~/store/deal-slide.store'

const store = useDealSlideStore()

const isLocalOpen = computed({
    get: () => store.isOpen,
    set: value => {
        store.isOpen = value
    }
})

</script>

<template>
    <div>
        <USlideover 
            v-model="isLocalOpen" 
            :ui="{overlay: { base: 'bg-gray-700/75' }}">
            <UCard
                class="flex flex-col flex-1 overflow-y-auto rounded-none"
                :ui="{
                    body: { base: 'flex-1' },
                    background: 'bg-gray-900',
                    ring: '',
                    divide: 'divide-y divide-border',
                }"
            >
                <template #header>
                    <KanbanSlideoverTop />
                </template>

                <KanbanSlideoverComments />
            </UCard>
        </USlideover>
    </div>
</template>