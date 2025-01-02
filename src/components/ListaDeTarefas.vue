<script setup>
const props = defineProps(['tarefas', 'tarefasPendentes', 'tarefasFinalizadas', 'listaTarefas'])
</script>

<template>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                    :id="tarefa.titulo" type="checkbox">
                <label :class="{ Done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                    {{ tarefa.titulo }}
                </label>
        </li>
    </ul>
    <ul v-if="tarefasPendentes">
        <h5>Não existe nenhuma tarefa pendente.</h5>
    </ul>
    <ul v-else-if="tarefasFinalizadas">
        <h5>Nenhuma tarefa foi finalizada.</h5>
    </ul>
</template>

<style scoped>
.Done {
    text-decoration: line-through;
}

ul {
    padding: 0;
}
</style>