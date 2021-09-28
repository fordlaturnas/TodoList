<template>
    <div class="todo-item" v-bind:class="{'is-completed':todoItemProp.completed }">
        <P>
            <!-- checkbox 33:03 in tutorial -->
            <input type="checkbox" v-on:change="markComplete">
            {{todoItemProp.title}}
            <!-- delete function using emit part 34:54 -->
            <button @click="$emit('del-todo', todoItemProp.id)" class="del">x</button>
        </P>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: [
        "todoItemProp"
        ],
    methods: {
        markComplete() {
            // checkbox  33:03 in tutorial
           this.todoItemProp.completed = !this.todoItemProp.completed
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-completed {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        border-radius: 50%;
        padding: 5px 9px;
        cursor: pointer;
        float: right;
    }
</style>