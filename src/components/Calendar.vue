<template>
<div id="tracker">
    <div id="calendar">
        <CalendarMonth :month="today" @prev-month="newMonth" @next-month="newMonth"></CalendarMonth>
        <div class="border">
            <CalendarWeek></CalendarWeek>
            <ol>
                <CalendarDay :days="today" :habits="habits"></CalendarDay>
            </ol>
        </div> 
    </div>
    <div id="habits">
        <AddHabit @add-habit="addHabit"></AddHabit>
        <Habits :habits="habits"></Habits>        
    </div>


</div>
</template>

<script>
import dayjs from "dayjs"
import CalendarMonth from "./CalendarMonth.vue"
import CalendarWeek from "./CalendarWeek.vue"
import CalendarDay from "./CalendarDay.vue"
import AddHabit from "./AddHabit.vue"
import Habits from "./Habits.vue"
export default {
    components: {
        CalendarMonth,
        CalendarWeek,
        CalendarDay,
        AddHabit,
        Habits
    },
    data() {
        return {
            today: dayjs(),
            habits: [
                {title: "reading", color: "#e66465", dates: ['9/4', '5/4']},
                {title: "dfdfg", color: "#eee", dates: ['4/4', '5/4']}
            ]
        }
    },
    methods: {
        newMonth(newMonth) {
            this.today = newMonth;
        },
        addHabit(newHabit) {
            if (newHabit.title != "")
                this.habits.push({title: newHabit.title, color: newHabit.color, dates: newHabit.dates })
        }
    }
}
</script>

<style scoped>
#tracker {
    display: flex;
}

#calendar {
    width: 65%;
}

#habits {
    width: 35%;
}

ol{
    display: grid;
    list-style: none;
    grid-template-columns: repeat(7, 1fr);
    margin: 0 0 0 0;
    padding: 0 0 0 0;
}

.border {
    border: solid 2px #e9e9e9;
    margin: 0 15px;
    height: auto;
    width: 60%;
}

</style>