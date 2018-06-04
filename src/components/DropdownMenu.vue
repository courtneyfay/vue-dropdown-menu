<template>
	<section class="dropdown-menu">
		<form 
			@submit.prevent.stop
			ref="dropdownmenu" 
			autofocus
			@blur="emitThing()"
			>
			<h1 class="dropdown-menu-heading">this is the dropdown menu</h1>
			<ol>
				<input type="radio">Apples</input>
				<input type="radio">Oranges</input>
				<input type="radio">Bananas</input>
			</ol>
			<button @click="emitThing()">Cancel</button>
			<button @click="emitThing()">Apply</button>
		</form>
	</section>
</template>

<script>
	export default {
		mounted() {
			this.$el.focus();
			console.log(document.activeElement);
		},
		props: {
			menuExpanded: {
				type: Boolean,
				default: true
			}
		},
		methods: {
			emitThing() {
				this.$emit('emit-a-thing');
			}
		}
	};
</script>

<style scoped>
	div {
		background-color: lightblue;
		position: relative;
		text-align: left;
		width: 300px;
		z-index: 2000px;
	}
	h1 {
		color: hotpink;
	}
</style>