<template>
    <div>
        <div v-bind:key="todoDataItemShow.id"  v-for="todoDataItemShow in todosDataProps">
           <TodoItem v-bind:todoItemProp="todoDataItemShow" v-on:del-todo="$emit('del-todo', todoDataItemShow.id)" />
        </div>
    </div>
</template> 

<script>
import TodoItem from './TodoITem'

export default { 
    name: "showtodos",
    components: {
        TodoItem
    },
    props: ["todosDataProps"]
}
</script> 

<style scoped>

</style>  