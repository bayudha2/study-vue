<template>
  <header>
      <h1>{{title}}</h1>
      <Button v-show="homePage" @btn-click="toggle" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red' : 'green'" />
  </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: {
            type: String,
            default: 'Hello John'
        },
        showAddTask: {
            type: Boolean
        }
    },
    components: {
        Button
    },
    methods: {
        toggle(){
            this.$emit('toggle-add-task')
        }
    },
    computed: {
        homePage(){
            if(this.$route.path === '/'){
                return true
            } else {
                return false
            }
        }
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

</style>