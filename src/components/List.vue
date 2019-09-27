<template>
    <div class="list-container">
        <div v-for="todo in items" :key="todo.id" class="todo-item">
            <p :class="{completed : todo.completed}">{{todo.task}}</p>
            <input type="checkbox" @click="toggleCompletion(todo.id)"/>
        </div>
    </div>
</template>

<script>
export default {
    props : {
        items : {
            type : Array
        }, 
        toggleCompletion : {
            type : Function
        }
    }
}
</script>

<style scoped>
    .list-container{
        margin:2rem 0;
    }

    .todo-item{
        background:#fff;
        border:1px solid #ccc;
        border-radius:.5rem;
        padding:1rem;
        margin-bottom:1rem;
        display:flex;
        align-items:center;
        justify-content: space-between;
        font-size:1.6rem;
    }

    .completed{
        text-decoration:line-through;
    }
</style>