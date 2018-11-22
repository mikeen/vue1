<template>
    <div class='ui centered card'>
        <transition name="slide-fade" mode="out-in">
        <div class="content" v-if="!isEditing" key="display">
        <div class='header'>
            {{ todo.title }}
        </div>
        <div class='meta'>
            {{ todo.project }}
        </div>
        <div class='extra content'>
            <span class='right floated edit icon' v-on:click="showForm">
            <i class='edit icon'></i>
            </span>
        </div>
        </div>
        <div class="content" v-else key="edit">
        <div class='ui form'>
            <div class='field'>
            <label>Title</label>
            <input type='text' v-model="todo.title" >
            </div>
            <div class='field'>
            <label>Project</label>
            <input type='text' v-model="todo.project" >
            </div>
            <div class='ui two button attached buttons'>
            <button class='ui basic blue button' v-on:click="hideForm">
                Close X
            </button>
            </div>
        </div>
        </div>
        </transition>
        
        <div class='ui bottom attached green basic button' v-if="!isEditing && todo.done" disabled key="statusCompleted">
            Completed
        </div>
        <div class='ui bottom attached red basic button' v-if="!isEditing && !todo.done"  key="statusPending">
            Pending
        </div>
    </div>
</template>

<script>
export default {
    props: ['todo'],
    data() {
        return {
            isEditing: false
        };
    },
    methods: {
        showForm() {
            this.isEditing = true;
        },
        hideForm() {
            this.isEditing = false;
        },
    },
};
</script>

<style>
/* Enter and leave animations can use different */
/* durations and timing functions.              */
.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>