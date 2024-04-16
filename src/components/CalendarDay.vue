<template>
    <li v-for="day in days.daysInMonth()" :key="day" :style="{ gridColumnStart: columnStart(day)}" v-on:click="showModal" >
        <modal-window ref="modal"></modal-window>
        <temolate v-for="habit in habits" :key="habit">
            <div v-if="habit.dates.includes(day + '/' + this.days.format('M'))" :style="{ backgroundColor: habit.color}">
                {{ habit.title }}
            </div>
        </temolate>
        
        <span :class="isToday(day)">{{ day }}</span>
    </li>
</template>

<script>
import dayjs from 'dayjs'
import ModalAddHabit from "./ModalAddHabit.vue"
export default {
    component: {
        ModalAddHabit
    },
    props:{
        days: {
            type: Object
        },
        habits: {
            type: Array
        }
    },
    methods: {
        columnStart(day) {
            let startColumn = (this.days.startOf("month").day() + day - 1)%7;
            if (startColumn == 0)
                startColumn = 7;
            return startColumn;
        },
        isToday(day){
            if (day == this.days.format('D') && this.days.format('M') == dayjs().format('M')){
                return {
                    isToday: true
                }
            }
        },
        show: function () {
            this.$refs.modal.show = true
        }
    }
}
</script>

<style scoped>
li {
    display: flex;
    border: 1px solid #e9e9e9;
    height: 100px;
    justify-content: flex-end;
    align-items: flex-end;
    
}

.isToday{
    background-color:red;
    padding: 5px;
    border-radius: 50px;

}

</style>
