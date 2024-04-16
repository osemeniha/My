<template>
<div>
    <p v-on:click="showAdd">Add Task</p>
    <div v-show="isShow">
        <input v-model="newTask.title" type="text">
        <div v-on:click="addTask">Готово</div>
    </div>
</div>
</template>

<script>
export default {
    data(){
        return{
           isShow: false,
           newTask: {title: "", done: false}
        }
    },
    methods: {
        showAdd() {
            this.isShow = !this.isShow;
        },
        addTask() {
            this.$emit("add-task", this.newTask);
            this.newTask.title = '';
        }       
    }

}
</script>