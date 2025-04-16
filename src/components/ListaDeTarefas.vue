<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <ul class="list-group mt-4">
        <li v-if="props.tarefas.length === 0"  class="list-group-item text-center">
            Não tem tarefas pendentes no momento.
        </li>
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" type="checkbox"
                :checked="tarefa.finalizada" :id="tarefa.titulo">
            <label :class="{ done: tarefa.finalizada === true }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>