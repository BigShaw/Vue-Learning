<template>
	<!-- @remove="tasks.splice(index, 1,'')" -->
	<div class="columns">
		<div class="column">
			<h1 class="title">All Tasks</h1>
			<div class="block">
				<ul class="tags">
					<li class="tag is-medium" v-for="(task, index) in tasks">
						{{task.description}}
						<a class="delete is-small" @click="tasks.splice(index, 1)"></a>
					</li>
				</ul>

				<div class="field is-grouped">
					<div class="control is-expanded">
						<input type="text" class="input" @keyup.enter="addTask" v-model="newDescription">
					</div>
					<div class="control">
						<a class="button" @click="addTask">Add Tasks</a>
					</div>
				</div>
				<div class="control">
					<label class="checkbox">
						<input type="checkbox" v-model="newCompleted">
						Is it completed?
					</label>
				</div>
			</div>
		</div>
		<div class="column">
			<div class="block">
				<h1 class="title">Completed Tasks</h1>
				<ul  class="tags">
					<li class="tag is-medium" v-for="task in tasks" v-if="task.completed">
						{{task.description}}
						<a class="delete is-small" @click="task.completed = false;"></a>
					</li>
				</ul>
			</div>
		</div>
		<div class="column">
			<div class="block">
				<h1 class="title">Incompleted Tasks</h1>
				<ul  class="tags">
				<li class="tag is-medium" v-for="task in tasks" v-if="!task.completed">
					{{task.description}}
					<a class="delete is-small" @click="task.completed = true;"></a>
				</li>
				<!-- <li class="tag is-medium" v-for="task in incompleteTasks" v-text="task.description"></li> -->
				</ul>
			</div>
		</div>
	</div>

</template>


<script type="text/javascript">
	export default{
		data(){
			return { 
				newDescription: '',
				newCompleted: false,
				tasks: [
				{ description: 'Go to the store', completed: true },
				{ description: 'Finish screencast', completed: false },
				{ description: 'Make donation', completed: false },
				{ description: 'Clear inbox', completed: false },
				{ description: 'Make dinner', completed: false },
				{ description: 'Clean room', completed: true }
				]
			};
		},

		computed: {
			incompleteTasks(){
				return this.tasks.filter(task => ! task.completed);
				// this.tasks.filter(function (task){
				// 	return ! task.completed;
				// })
			}
		},

		methods: {
			addTask() {
				this.tasks.push({
					description: this.newDescription,
					completed: this.newCompleted
				}),
				this.newDescription = '';
			},
			removeTask(index) {
				this.tasks.splice(index, 1);
			},
			isNotCompleted(index) {
				this.tasks[index].completed = false;
			}
		}
	}
</script>


<style type="text/css">


</style>