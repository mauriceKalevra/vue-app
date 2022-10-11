<template>
    <ul>
        <li v-for="(todo, index) in todos" v-bind:key="todo.id"
        :class="{'finishedTask':todo.finished}">
        <input type="checked" checked v-if="finished" />
        <input type="checkbox" :checked="todo.finished" />
        <a :href="'?id='+todo.id">show</a>
        {{++index}}.{{todo.name}}

        </li>
    </ul>



</template>

<script>
export default {
    name: "TodoList"

}
</script>

<style>

</style>