<template>
    <div v-for="habit in habits" :key="habit">
        <p :style="{border: styleOfHabit(habit)}">{{ habit.title }}</p>
    </div>
</template>

<script>
export default {
    props: {
        habits: []
    },
    methods: {
        styleOfHabit(habit) {
            return "solid 2px" + habit.color;
        }
    }
}
</script>