<template>
    <div>
        <h2>Manage Goals</h2>
        <input type="text" ref="goal">
        <button @click="setGoal">Set Goal</button>
        <teleport to="#app">
        <error-page v-if="goalIsValid">
            <h2>No Goal Set</h2>
            <p>please set a goal</p>
            <button @click="resetGoal">Okay</button>
        </error-page>
    </teleport>
    </div>
</template>
<script>
    import ErrorPage from './ErrorPage.vue';
    export default {
        data(){
            return {
                goalIsValid: true
            }
        },
        components:{
            ErrorPage
        },
        methods: {
            setGoal(){
                
                if(this.$refs.goal.value !== ''){
                    console.log('hello world');
                    this.goalIsValid = false;
                    return;
                }
                console.log('test');
                this.goalIsValid = true;
            },
            resetGoal(){
                this.goalIsValid = false;
            }
        }
    }
</script>

