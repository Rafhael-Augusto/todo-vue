<script setup>
    const props = defineProps(['tarefasPendentes'])
</script>

<template>
    <header class="p-5 mb-44 mt-4 bg-light rounded-3">
        <h1>Minhas tarefas</h1>
        <p v-if="props.tarefasPendentes >= 1">
            Você possui {{ props.tarefasPendentes }}
            tarefa{{ props.tarefasPendentes > 1 ? 's' : '' }}
            pendente{{ props.tarefasPendentes > 1 ? 's' : '' }}.
        </p>
        <p v-else>Você possui nenhuma tarefa pendente</p>
    </header>
</template>