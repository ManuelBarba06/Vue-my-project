<template>
    <div class="my-component">
        <h1 v-bind:class="{highlighted: isHighlighted}">{{ title }}</h1>
        <button @click="toggleHighlight">Toogle Hightlight</button>
        <input v-model="message"/>
        
        <ul>
            <li v-for="item in list" :key="item.id">{{item.text}}</li>
        </ul>
    </div>
</template>

<style scoped>
.highlighted {
    color: gold;
}
</style>

<script>
    export default {
        name: "MyComponent",
        data() {
            return {
                message: "Hello World with Vue!",
                title: 'This is the title',
                isHighlighted: false,
                isVisible: true,
                list: [
                    {id: 1, text: "First item"},
                    {id: 2, text: "Second item"},
                    {id: 3, text: "Third item"}
                ]
            }
        },
        methods: {
            toggleVisibility() {
                this.isVisible = !this.isVisible
            },
            sayHello() {
                alert('Hello!')
            },
            toggleHighlight() {
                this.isHighlighted = !this.isHighlighted
            }
        }
    }
</script>