<template>
    <div>
        Filter Todos:
        <select @change="filterTodos($event)">
            <option value="200">200</option>
            <option value="100">100</option>
            <option value="50">50</option>
            <option value="20">20</option>
            <option value="10">10</option>
        </select>
    </div>
</template>

<script>
import { mapActions } from 'vuex';

export default {
    name: 'FilterTodos',
    methods: {
        ...mapActions(['filterTodos']),
        filterTodos(event) {
            // filter based on the selected value
            const selectedValue = event.target.value;

            // Dispatch the action with the selected value
            this.$store.dispatch('filterTodos', selectedValue);
        }
    }
}
</script>

<style scoped>
select {
    margin-top: 20px;
    padding: 6px;
    border: #41b883 1px solid;
}
</style>
