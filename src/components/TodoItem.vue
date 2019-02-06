<template>
    <div :class="[
            'todo-item',
            { 'is-complete': todo.completed }
        ]"
    >
        <p>
            <input type="checkbox" @change="markComplete">
            {{ todo.title }}
             <button class="del" @click="$emit('delItem', todo.id)">x</button>
        </p>
    </div>
</template>

<script>
    export default  {
        name: 'TodoItem',
        props: {
            todo: {
                type: Object
            }
        },
        methods: {
            markComplete() {
                this.todo.completed = !this.todo.completed;
            }
        }
    }
</script>

<style scoped>

    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
    
</style>