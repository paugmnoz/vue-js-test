<template>
  <div class="users">
    <h1>Users</h1>
    <form v-on:submit="addUser">
      <input type="text" name="" id="" v-model="newUser.name" placeholder="Enter name">
      <br/>
      <input type="text" name="" id="" v-model="newUser.email" placeholder="Enter mail">
      <br/>
      <input type="submit" value="Submit">
      <br/>
    </form>

    <ul>
      <li v-for="user in users">
        <input type="checkbox" name="" id="" class="toggle" v-model="user.contacted">
        <span :class="{contacted: user.contacted}">
          {{user.name}}: {{user.email}}
          <button v-on:click="deleteUser(user)">x</button>
        </span>
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
                users: [{
                    name: "Paula G",
                    email: "pg@gmail.com",
                    contacted: false
                }, {
                    name: "Tom G",
                    email: "tom@gmail.com",
                    contacted: false
                }, {
                    name: "Nick G",
                    email: "nick@gmail.com",
                    contacted: false
                }, {
                    name: "Jules G",
                    email: "jj@gmail.com",
                    contacted: false
                }]
            }
        },

        methods: {
            addUser: function(e) {
                this.users.push({
                    name: this.newUser.name,
                    email: this.newUser.email,
                    contacted: false
                });
                e.preventDefault();
            },
            deleteUser: function(user) {
                this.users.splice(this.users.indexOf(user), 1);
            }
        },

        created: function() {
            this.$http.get('https://jsonplaceholder.typicode.com/users')
                .then(function(response) {
                    console.log(response.data);
                });
        }

    }
</script>

<style scoped>
    .contacted {
        text-decoration: line-through;
    }
</style>