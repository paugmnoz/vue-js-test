<template>
  <div class="test">
    <h1>{{title}}</h1>
    <span v-html="title2"> </span>
    <p>{{user.first_name}}</p>
    <p v-text='user.first_name'></p>
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
                active: true
            }
        }
    }
</script>

<style scoped>

</style>