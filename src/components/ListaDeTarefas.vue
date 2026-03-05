<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
    <div class="mt-4">

        <ul v-if="props.tarefas.length" class="list-group">
            <li class="list-group-item" v-for="tarefa in props.tarefas" :key="tarefa.titulo">
                <input type="checkbox" :checked="tarefa.finalizada"
                    @change="evento => tarefa.finalizada = evento.target.checked" :id="tarefa.titulo">

                <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                    {{ tarefa.titulo }}
                </label>
            </li>
        </ul>

        <p v-else class="text-center mt-4">
            Nenhuma tarefa encontrada
        </p>

    </div>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>