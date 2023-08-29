<script setup>
    defineProps({
    task: String,
    })

    import { ref } from 'vue'

    const complete = ref(false)
    const active = ref(true)
</script>

<template>
    <div v-if="active">
        <div class="listitem">
            <s v-if="complete"><h3>{{ task }}</h3></s>
            <h3 v-else>{{ task }}</h3>
            <button @click="complete = !complete">✓</button>
            <button @click="active = false" v-if="complete" class="closer">✕</button>
        </div>
        <br>
    </div>
</template>

<style scoped>
    .listitem {
        display: inline-flex;
        margin: 5px;
    }

    h3 {
        margin-right: 10px;
    }

    button{
        display: inline-block;
        vertical-align: middle;
        background-color: #4CAF50;
        border: none;
        color: white;
        padding: 5px 5px;
        text-align: center;
        text-decoration: none;
        font-size: 16px;
        border-radius: 25%;
        margin-right: 5px;
    }

    .closer {
        background-color: red;
    }
</style>