<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>My name is : {{name}}</p>
        <button @click="resetName">Reset Name</button>
        <button @click="resetFn">Reset Name</button>
        <p>My age is {{age}}</p>
    </div>
</template>

<script>
    import {eventBus} from '../main';

    export default{
        // props: ['name']
        props: {
            name: {
                type: String
            },
            resetFn: {
                type: Function
            }
        },
        methods: {
            resetName(){
                // this.name = "Daniel"
                this.$emit('nameWadReset', 'Daniel' );
            }
        },
        data: function(){
            return {
                age: '27'
            }
        },
        created(){
            eventBus.$on('ageWasChanged',(ages)=>{
                this.age = ages
            })
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
