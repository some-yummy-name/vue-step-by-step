<template>
    <div :id="href" v-show="isActive">
        <slot></slot>
    </div>
</template>

<script>
	export default {
		name: "Tab",
		data() {
			return {
				isActive: false
			}
		},
		props: {
			name: { required: true },
			selected: { default: false }
		},
		mounted() {
			this.isActive = this.selected
		},
		computed: {
			href() {
				return this.name.toLowerCase().replace(/ /g, "-");
			}
		}
	}
</script>

<style scoped>

</style>
