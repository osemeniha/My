<template>
    <Tasks :tasks="tasks"></Tasks>
    <AddTask @add-task="addNewTask"></AddTask>
</template>

<script>
import Tasks from "./Tasks.vue";
import AddTask from "./AddTask.vue";
export default {
    components: {
        Tasks,
        AddTask
    },
    data() {
        return {
            tasks: [
                {title: "bread", done: false}
            ]
        }
    },
    methods: {
        addNewTask(newTask) {
            if(newTask.title != "")
                this.tasks.push({title: newTask.title, done: false});
        }
    }
}
</script>