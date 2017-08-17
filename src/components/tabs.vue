<template>
	<div>
		<div class="tabs">
			<ul>
				<li v-for='tab in tabs' :class="{ 'is-active': tab.isActive }">
					<a :href="tab.href" @click="selectTab(tab)">{{ tab.name }}</a>
				</li>
			</ul>
		</div>

		<div class="tabs-details">
			<slot></slot>
		</div>
	</div>

</template>

<script>
	export default{
		name: 'tabs',
		data(){
			return { 
				tabs:[]
			};
		},
		methods: {
			selectTab(selectTab){
				this.tabs.forEach(tab => {
					tab.isActive = (tab.name == selectTab.name)
				})
			}
		},
		created(){
			this.tabs = this.$children;
		}
	}

</script>