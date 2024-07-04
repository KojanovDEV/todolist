<template>
    <body>
    <div class="container">
        <div id="newtask">
        <input type="text" v-model="newTodo" placeholder="Yangi ishni joylashtirish ..." />
        <button @click="addTodo()">Qo'shish</button>
        <div id="tasks">
            <ul>
            <li class="task" v-for="(todo, index) in todos" :key="index">
                {{ todo }}
                <button @click="removeTodo(index)"><i class="far fa-trash-alt"></i></button>
            </li>
        </ul>
        </div>
        </div>
    </div>
    </body>
</template>

<script>
export default {
    data() {
        return {
            newTodo: '',
            todos: []
        }
    },
    methods: {
        addTodo() {
            if (!this.newTodo) return
            this.todos.unshift(this.newTodo)
            this.newTodo = ''
        },
        removeTodo(index) {
            this.todos.splice(index, 1)
        }
    }
}
</script>

