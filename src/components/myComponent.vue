<template>
    <div class="test">
        <input type="text" v-model="input"><br></br>
        <h1>{{input}}</h1>
        <h2>{{message}}</h2>
        <p v-text="name" v-if="active"></p>
        <p v-else>something else</p>
        <ul>
            <li v-for="_ in things" :key="_.thing">{{_.thing}}</li>
        </ul>
        <button v-on:click="push">Push me</button>
        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterPressed">
        <hr></hr>
        <label>first name</label><input type="text" v-model="name">
        <br></br>
        <label>last name</label><input type="text" v-model="lastName">
        <h3>{{fullName}}</h3>
        <h2>{{something}}</h2>
    </div>
</template>

<script>
    export default {
        name : 'myComponent',
        props : {
            something : {
                type    : String,
                default : 'im the default value'
            }
        },
        data(){
            return {
                input       : '',
                message     : 'lello',
                name        : 'michal',
                lastName    : 'stachnik',
                active      : true,
                things      : [
                    { thing : 'one' },
                    { thing : 'two' },
                    { thing : 'three' }
                ],
                push: function(){
                    alert('I was pushed')
                },
            }
        },
        methods : {
            pressKey : function(e){
                console.log(e.target.value)
            },
            enterPressed : function(){
                console.log('enter pressed')
            }
        },
        computed : {
            fullName : function(){
                return this.name + ' ' + this.lastName
            } 
        }
    }
</script>

<style scoped>
    ul{
        list-style: none;
        padding: 0;
    }
</style>