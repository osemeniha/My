<template>
    <div v-on:click="showAdd">Добавить трекер</div>
    <div v-show="isShow">
        <input type="text" v-model="newHabit.title">
        <input type="color" v-model="newHabit.color">
    </div>
    <button v-on:click="addHabit">Готово!</button>
</template>

<script>
export default {
    data() {
        return {
            isShow: false,
            newHabit: { title: "", color: "", dates: ""}
        }
    },
    methods: {
        showAdd() {
            this.isShow = !this.isShow;
        },
        addHabit() {
            this.$emit("add-habit", this.newHabit);
            this.newHabit.title = "";
            this.newHabit.color = "";
        }
    }
}
</script>

