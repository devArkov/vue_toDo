<template>
    <div class="todo">
        <h1>Todo app</h1>
        <div class="task" v-for="(task, key) in tasks" :key="key">
            <div class="title"><strong>Заголовок:</strong>{{ task.title }}</div>
            <div class="text"><strong>Текст</strong>{{ task.text }}</div>
        </div>
    </div>    
</template> 

<script>
    export default {
        name: 'Todo',
        data() {
            return {
                tasks: [
                    {id: 1, title: 'Задача 1', text: 'Подробно о задаче 1'},
                    {id: 2, title: 'Задача 2', text: 'Подробно о задаче 2'},
                    {id: 3, title: 'Задача 3', text: 'Подробно о задаче 3'},
                    {id: 4, title: 'Задача 4', text: 'Подробно о задаче 4'},
                ]
            }
        }
    }
</script>

<style scoped>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .todo {
        padding: 15px;
    }

    .task {
        margin-top: 15px;
        padding: 15px;
        border: 2px solid teal;
    }

    .text {
        margin-top: 10px;
    }
</style>