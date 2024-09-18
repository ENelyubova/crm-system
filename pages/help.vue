<script setup lang="ts">
const questions = [
    {
        title: 'Как зарегистрироваться на сайте?', text: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod.'
    },
    {
        title: 'Возможности и преимущества CRM', text: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod.',
    },
    {
        title: 'Настройки', text: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod.',
    },
    {
        title: 'Общие вопросы', text: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quo, quod.',
    },
]
</script>

<template>
    <div class="p-10 srelative w-full overflow-hidden">
        <h1 class="font-bold text-2xl mb-10">Вопросы и ответы</h1>
        <LayoutQuestionItem 
            v-for="q in questions"
            :key="q.title"
            :question="q"
        />
    </div>
</template>