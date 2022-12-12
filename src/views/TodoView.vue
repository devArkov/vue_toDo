<template>
    <div class="todo">
        <h1>Todo app</h1>

        <form @submit.prevent>
            <h3>Добавить задачу</h3>
            <input 
            v-bind:value="title"
            @input="title = $event.target.value"
            type="text" 
            class="input" 
            placeholder="Название задачи">

            <input 
            v-bind:value="text"
            @input="text = $event.target.value"
            type="text" 
            class="input" 
            placeholder="Описание задачи">

            <button 
            type="submit" 
            class="btn" 
            @click="addTask">
            Добавить
            </button>
        </form>

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
                ],
                title: '',
                text: ''
            }
        },

        methods: {
            addTask() {
                const newTask = {
                    id: Date.now(),
                    title: this.title,
                    text: this.text
                }
                this.tasks.push(newTask);
                this.title = '';
                this.text = '';
            }
        }
    }
</script>

<style scoped lang="scss">
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    h3 {
        text-align: left;
    }

    form {
        display: flex;
        flex-direction: column;
    }

    .input {
        width: 100%;
        margin-top: 15px;
        padding: 10px 15px;
        border: 2px solid teal;
    }

    .btn {
        align-self: flex-end;
        margin-top: 15px;
        padding: 10px 15px;
        border: 2px solid teal;
        background-color: transparent;
        transition: .5s;

        &:hover {
            border: 2px solid teal;
            background-color: teal;
            color: #fff;
            cursor: pointer;
        }
       
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