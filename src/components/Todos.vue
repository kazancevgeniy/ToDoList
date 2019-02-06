<template>
	<div>
		<div v-for="todo in todos" :key="todo.id">
			<TodoItem :todo="todo" @delItem="$emit('delItem', todo.id)"/>
		</div>
	</div>
</template>

<script>
import TodoItem from './TodoItem';
	export default {
		name: 'Todos',
		components: {
			TodoItem
		},
		props: {
			todos: {
				type: Array
			}
		},
		methods: {
			// delTodo() {
   //          	this.$emit('delTodo', this.todo.id);
   //      	}
        }
	}
</script>

<style scoped>
	
</style>