<template>
	<div>
		<h1>{{this.getFullName}}</h1>
		<div v-for="todo in todos" :key="todo.id">
			<h3>
				<TodoItem />
			</h3>
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
		data() {
			return {
				person : {
					name: 'Evgeniy',
					secondName: 'Kazancev',
					birdth: 1990,
					marryed: false
				}
			}
		},
		computed: {
			getFullName() {
				return `${this.person.name + ' ' + this.person.secondName}`
			}
		}
	}
</script>

<style scoped>
	
</style>