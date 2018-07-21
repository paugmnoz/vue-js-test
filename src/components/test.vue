<template>
  <div class="test">
    <h1>{{title}}</h1>
    <input type="text" v-model="title" name="" id="">
    </br>
    <span v-html="title2"> </span>
    <p v-if="showName">{{user.first_name}} showname is true</p>
    <p v-else="showName">{{user.first_name}} showname is false</p>
    <p v-text='user.first_name'></p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet('Hi')">Say hi</button>
    <input type="text" name="" id="" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
  </div>
</template>

<script>
    export default {
        name: 'test',

        data() {
            return {

                title: 'Helloooo Vue!',
                title2: '<h1>This is shown with the v-html</h1>',
                user: {
                    first_name: 'Paula',
                    last_name: 'Garcia'
                },
                showName: false,
                items: [{
                    title: 'Item 1'
                }, {
                    title: 'Item 2'
                }, {
                    title: 'Item 3'
                }]
            }

        },

        methods: {
            greet: function(greeting) {
                alert(greeting);
            },
            pressKey: function(e) {
                console.log(e.target.value);
            },
            enterHit: function() {
                console.log('You hit enter');
            }

        }
    }
</script>

<style scoped>

</style>