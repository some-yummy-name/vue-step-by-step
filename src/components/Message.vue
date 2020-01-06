<template>
    <div class="message">
        <div class="message__title">{{title}}</div>
        <div class="message__body">{{body}}</div>
    </div>
</template>

<script>
	export default {
		props: ['title', 'body'],
	}
</script>

<style lang="scss">
    .message {
        border: 1px solid;

        &__title{
            font-weight: 700;
        }
    }
</style>
