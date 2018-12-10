<template>
    <div id="app">
        <!-- <test msg="哈哈，这是新的默认值"></test> -->
        <users></users>
    </div>
</template>
<script>
import Test from './components/Test'
import Users from './components/Users'

export default {
    name: 'App',
    components: {
        Test,
        Users
    }
}
</script>
<style>
</style>
