<script setup lang="ts">
import { defineProps } from 'vue'

defineProps(['question'])
</script>

<template>
    <UiAccordion type="single" collapsible>
        <UiAccordionItem value="item-1">
            <UiAccordionTrigger>{{ question.title }}</UiAccordionTrigger>
            <UiAccordionContent >{{ question.text }}</UiAccordionContent>
        </UiAccordionItem>
    </UiAccordion>
</template>