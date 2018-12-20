<template>
    <div class="TestClass">
        <h1>{{title}}</h1>
        <p>{{user.first_name}}</p>
        <p>{{user.last_name}}</p>
        <p>inside test</p>
    </div>
</template>

<script>
    export default {
        // name: 'TestComponent',
        data() {
            return {
                title: 'Hello World',
                user: {
                    first_name: 'John',
                    last_name: 'Doe'
                }
            }
        }
    }
</script>

<style scoped>

</style>

