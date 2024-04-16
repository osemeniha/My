<template>
<div>
    <div v-for="(task, index) in tasks" :key="index" class="task flex">
        <div class="flex">
            <input type="checkbox" v-model="task.done">
            <p>{{ task.title }}</p>            
        </div>
        <p id="delete" v-on:click="removeTask(index)">🗑️</p>

    </div>
    
</div>
</template>

<script>
export default {
    props: {
        tasks: []
    },
    methods: {
        removeTask(index){
            this.tasks.splice(index, 1);
        }        
    }

}
</script>

<style scoped>
.flex {
    display: flex;
    justify-content: space-between;
}
.task {
    background-color: #e9e9e9;
    border-radius: 5px;
    margin: 10px;
    width: 300px;
}

</style>