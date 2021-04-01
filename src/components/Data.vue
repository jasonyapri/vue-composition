<template>
    <h2>Options: {{ o_firstName }}</h2>
    <h2>Options: {{ o_firstName }} {{ o_lastName }} a.k.a {{ o_heroName }}</h2>
    <hr>
    <h2>Composition: {{ c_firstName }}</h2>
    <h2>Composition: {{ greet }}</h2>
    <hr>
    <h2>Composition: {{ c_firstName }} {{ c_lastName }} {{ c_heroName }}</h2>
    <h2>Composition: {{ greetHero }}</h2>
    <hr>
    <h2>Composition: {{ state.firstName }} {{ state.lastName }} {{ state.heroName }}</h2>
    <h2>Composition: {{ reactiveGreetHero }}</h2>
</template>

<script>
    import { ref, reactive } from 'vue'

    export default {
        name: 'Data', 
        setup() {
            const c_firstName = ref('Clark')
            const c_lastName = ref('Kent')
            const c_heroName = ref('Superman')

            //console.log('c_firstName: ', c_firstName)
            
            const greet = `Hello ${c_firstName.value}`
            const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`

            const state = reactive({
                firstName: 'Princess',
                lastName: 'Diana',
                heroName: 'Wonder Woman',
            })

            const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`

            const isLoggedIn = ref(false) // Use ref when we are dealing with a single primitive data types
            const isLoggedInReactive = reactive({
                value: false
            }) // Don't use reactive when  you only want to store one primitive data type, use it only when we are dealing with an object with many variables

            return {
                c_firstName, // similar to `c_firstName: c_firstName`
                c_lastName,
                c_heroName,
                greet,
                greetHero,
                reactiveGreetHero,
                state,
                isLoggedIn,
                isLoggedInReactive
            }
        },
        data() {
            return {
                o_firstName: 'Bruce',
                o_lastName: 'Wayne',
                o_heroName: 'Batman',
            }
        }
    }
</script>

<style scoped>

</style>