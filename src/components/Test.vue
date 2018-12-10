<template>
    <div class="test">
        <!-- 获取数据 -->
        <h1>{{title}}</h1>
        <p>{{user.firstName}}</p>
        <p v-text="user.lastName"></p>
        <!-- v-if -->
        <p v-if="showName">{{user.lastName}}</p>
        <p v-else="showName">Nobady</p>
        <!-- v-for -->
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>
        <!-- v-on -->
        <button v-on:click="greet('Hello,everyone')">Say Greeting</button>
        <!-- 键盘事件 -->
        <input type="text" v-on:keyup="pressKey" v-on:keyup.alt.enter="enterHit">
        <hr>
        <!-- computed 计算属性 -->
        <label>First Name:</label>
        <input type="text" v-model="user.firstName">
        <br>
        <label>Last Name:</label>
        <input type="text" v-model="user.lastName">
        <br>
        <h3>{{fullName}}</h3>
        <!-- props 属性 -->
        <h2>{{msg}}</h2>
    </div>
</template>
<script>
export default {
    name: "test",
    props: {
        msg: {
            type: String,
            default: "默认就是这样"
        }
    },
    data() {
        return {
            title: "hallo,vue.js!",
            user: {
                firstName: "jiajie",
                lastName: "Wu"
            },
            showName: false,
            items: [{
                title: 'item 1'
            }, {
                title: 'item 2'
            }, {
                title: 'item 5'
            }]
        }
    },
    methods: {
        greet: function(greeting) {
            alert(greeting);
        },
        pressKey: function() {
            console.log("please......");
        },
        enterHit: function() {
            console.log("Entering!!!!!!");
        }
    },
    computed: {
        fullName: function() {
            return this.user.firstName + " " + this.user.lastName;
        }
    }
}
</script>
<style scoped>
</style>
