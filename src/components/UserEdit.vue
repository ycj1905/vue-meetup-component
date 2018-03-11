<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <button @click="changeAge">change Age</button>
    </div>
</template>

<script>

    import {eventBus} from '../main';

    export default {
        methods: {
            changeAge(){
                eventBus.$emit('ageWasChanged', this.age);
            }
        },
        data: function(){
            return {
                age: 30
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
