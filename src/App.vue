<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <input type="text" v-model="message">
        <Task>name</Task>
        <Task>another</Task>
        <div>{{message}}</div>
        <ul>
            <li v-for="(item,index) in list" :key="index">{{item}}</li>
        </ul>
        <ul>
            <li v-for="(item,index) in upperList" :key="index">{{item}}</li>
        </ul>
    </div>
</template>

<script>
    import Task from "./components/Task"

	export default {
		name: 'app',
		components: {
			Task
        },
		data() {
			return {
				message: "",
				list: ["one", "two"]
			}
		},
		computed: {
			upperList() {
				return this.list.map(item => item.toUpperCase());
			}

		}
	}
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
