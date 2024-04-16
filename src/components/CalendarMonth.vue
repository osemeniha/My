<template>
<div>
    <p v-on:click="prevMonth"><-----</p>
    <p>{{ month.format('MMMM') }}</p>
    <p v-on:click="nextMonth">-----></p>
</div>
</template>

<script>
import dayjs from "dayjs"
export default {
    props: {
        month: {
            type: Object
        }
    },
    methods: {
        prevMonth() {
            let newMonth = dayjs(this.month).subtract(1, "month");
            this.$emit("prev-month", newMonth);
        },
        nextMonth() {
            let newMonth = dayjs(this.month).add(1, "month");
            this.$emit("next-month", newMonth);
        }
    }
}
</script>

<style scoped>
div{
    display:flex;
    justify-content: center;

}
p {
    margin: 10px 50px;
}
</style>