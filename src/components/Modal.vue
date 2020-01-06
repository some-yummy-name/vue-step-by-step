<template>
    <div class="modal is-active">
        <div class="modal-background" @click="$emit('close')"></div>
        <div class="modal-content">
            <!-- Any other Bulma elements you want -->
            <div class="box">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi aperiam consectetur debitis deleniti
                eaque
                enim ex, excepturi, expedita in iure laborum mollitia, nesciunt praesentium repudiandae rerum
                tempore
                veniam
                veritatis voluptatem?
            </div>
        </div>
        <button class="modal-close is-large" aria-label="close" @click="$emit('close')"></button>
    </div>
</template>

<script>
	export default {
		name: "Modal"
	}
</script>

<style scoped>

</style>
