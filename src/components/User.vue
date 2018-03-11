<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <p>My name is : {{name}}</p>
        <button @click="changeName">change name to Yu</button>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :name = "name" @nameWadReset="testFn($event)" :resetFn = "resetName2"></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        },
        data: function(){
            return {
                name: 'Matt'
            }
        },
        methods: {
            changeName(){
                this.name = 'Yu'
            },
            resetName2(){
                this.name = 'Danel'
            },
            testFn(data){
                console.log(data)
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
