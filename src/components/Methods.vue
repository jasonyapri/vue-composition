<template>
    <div>
        <h2>{{ name }}</h2>
        <button @click="setName">Change Name</button>
    </div>

    <div>
        <h2>{{ count }}</h2>
        <button @click="incrementCount">Increment Count</button>
    </div>

    <h2>{{ first }} {{ last }}</h2>
    <button @click="changeHero">Change Hero</button>
</template>

<script>
    import { ref, reactive, toRefs } from 'vue'

    export default {
        name: 'Methods',
        setup() {
            const count = ref(0)

            function incrementCount() {
                count.value++
            }

            const state = reactive({
                first: 'Bruce',
                last: 'Wayne'
            })

            function changeHero() {
                state.first = 'Clark',
                state.last = 'Kent'
            }

            return {
                count,
                incrementCount,
                ...toRefs(state),
                changeHero,
            }
        },
        data() {
            return {
                name: 'Jason'
            }
        },
        methods: {
            setName() {
                this.name = 'Codevolution'
            }
        },
    }
</script>

<style scoped>

</style>