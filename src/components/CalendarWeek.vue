<template>
    <ul>
        <li v-for="day in days" :key="day">{{ day }}</li>
    </ul>
</template>

<script>
export default {
    data() {
        return {
            days: ['MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT', 'SUN']
        }
    }
}
</script>

<style scoped>

ul{
    display: grid;
    list-style: none;
    grid-template-columns: repeat(7, 1fr);
    margin: 0 0 0 0;
    padding: 0 0 0 0;
    height: 50px;
}

li {
    display: flex;
    border: 1px solid rgb(203 213 225);
    justify-content: flex-end;
    align-items: flex-end;
    
    
}
</style>