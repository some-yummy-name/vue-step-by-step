<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <input type="text" v-model="message">
        <Task>name</Task>
        <Task>another</Task>
        <Message title="text" body="body"></Message>
        <div>{{message}}</div>
        <ul>
            <li v-for="(item,index) in list" :key="index">{{item}}</li>
        </ul>
        <ul>
            <li v-for="(item,index) in upperList" :key="index">{{item}}</li>
        </ul>
        <button @click="toggleModal(true)">show modal</button>
        <Modal v-show="showModal" @close="toggleModal(false)"></Modal>
        <Tabs>
            <Tab name="About" :selected="true">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Alias, beatae!
            </Tab>
            <Tab name="History">
                History
            </Tab>
        </Tabs>
    </div>
</template>

<script>
	import Task from "./components/Task"
	import Message from "./components/Message"
	import Modal from "./components/Modal"
	import Tabs from "./components/Tabs"
	import Tab from "./components/Tab"

	export default {
		name: 'app',
		components: {
			Task,
			Message,
			Modal,
			Tabs,
			Tab
		},
		data() {
			return {
				message: "",
				list: ["one", "two"],
				showModal: false
			}
		},
		computed: {
			upperList() {
				return this.list.map(item => item.toUpperCase());
			}

		},
		methods: {
			toggleModal(show) {
				if (show) {
					this.showModal = true;
					document.querySelector("html").classList.add("is-clipped");
				} else {
					this.showModal = false;
					document.querySelector("html").classList.remove("is-clipped");
				}
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
