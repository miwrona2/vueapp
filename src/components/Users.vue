<template>
    <div class="users">
        <h1>Users</h1>
        <form v-on:submit="addUser">
            <input type="text" v-model="newUser.name" placeholder="Type name"><br />
            <input type="text" v-model="newUser.email" placeholder="Type email"><br />
            <input type="submit" value="Dodaj">
        </form>
        <ul>
            <li v-for="user in users"> 
                <input type="checkbox" class="toggle" v-model="user.contacted">
                <span :class="{contacted: user.contacted}">{{ user.name }}: {{ user.email }}</span>
                <button v-on:click="deleteUser(user)">x</button>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'users',
        data() {
            return {
                newUser: {},
                users: [
                    {
                        name: 'John Doe',
                        email: 'jdoe@gmail.com',
                        contacted: false
                    },
                    {
                        name: 'Steve Smith',
                        email: 'ssmith@gmail.com',
                        contacted: false
                    },
                    {
                        name: 'Tom Whit',
                        email: 'twhite@gmail.com',
                        contacted: false
                    },
                ]
            }
        },
        methods: {
            addUser: function(e){
                this.users.push(
                    {
                        name: this.newUser.name,
                        email: this.newUser.email,
                        contacted: false,
                    }
                );
                e.preventDefault();
            },
            deleteUser: function(user){
                this.users.splice(this.users.indexOf(user), 1)
            }
        }, 
        created: function(){
            this.$http.get('https://jsonplaceholder.typicode.com/users').then(function(response){
                this.users = response.data;
            });
        }
    }
</script>

<style scoped>
    .contacted{
        text-decoration-line: line-through;
    }
</style>

