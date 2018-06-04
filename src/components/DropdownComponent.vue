<template>
	<div @click="hasFocus()" ref="outerdiv">
		<h1 class="dropdown-heading" ref="heading">Vue Dropdown Menu experiment</h1>
		<div class="dropdown-background" ref="dropdownarea">
			<button @click="toggleMenu()" ref="dropdownbutton">Dropdown \/</button>
			<dropdown-menu v-if="menuExpanded" :menuExpanded="menuExpanded" @emit-a-thing="toggleMenu()"></dropdown-menu>
		</div>
	</div>
</template>

<script>
	import DropdownMenu from './DropdownMenu.vue';

	export default {
		components: {
			DropdownMenu
		},
		data() {
			return {
				menuExpanded: false
			};
		},
		methods: {
			toggleMenu() {
				console.log("toggleMenu: " + this.menuExpanded);
				this.menuExpanded = !this.menuExpanded;

				return;
			},
			hasFocus() {
				console.log(document.activeElement);
			}
		}
	};
</script>

<style scoped>
	.dropdown-heading {
		color: orange;
		font-weight: bold;
		text-align: center;
	}
	button {
		color: turquoise;
	}
	.dropdown-menu-heading {
		color: hotpink;
	}
	.dropdown-menu {
		background-color: lightblue;
		text-align: left;
		width: 300px;
	}
	.dropdown-background {
		background-color: lightsalmon;
		margin: 0;
	}
</style>