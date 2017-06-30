<template>
    <div class="users">
        <h1>Users Component</h1>
        <form v-on:submit="addUser">
            <input type="text" v-model="newUser.name" placeholder="name">
            <br></br>
            <input type="submit" value="submit">
        </form>
        <ul>
            <li v-for="user in users" :key="user.name">
                <input type="checkbox" class="toggle" v-model="user.active">
                <span :class="{active: user.active}">
                    {{user.name}}
                    <button v-on:click="deleteUser(user)">X</button>
                </span>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name : 'users',
        data(){
            return {
                newUser : {},
                users : [
                    { 
                        name : 'Alice',
                        active : false
                    },
                    {
                        name : 'Bob',
                        active : false
                    },
                    {
                        name : 'Charlie',
                        active : false
                    }
                ]
            }
        },
        methods : {
            addUser : function(e){
                console.log('addUser fired')
                e.preventDefault()
                this.users.push({
                    name    : this.newUser.name,
                    active  : false
                })
            },
            deleteUser : function(user){
                this.users.splice(this.users.indexOf(user), 1)
            }
        },
    }
</script>

<style scoped>
    ul{
        list-style: none;
        padding: 0;
    }
    .active{
        text-decoration: line-through;
    }
</style>