<template>
  <nav class="filter-nav">
    <button @click="updateFilter('all')" :class="{active:current === 'all' }">View All</button>
    <button @click="updateFilter('Copmleted')" :class="{active:current === 'Copmleted' }">Copmleted</button>
    <button @click="updateFilter('Ongoing')" :class="{active:current === 'Ongoing' }">Ongoing</button>
  </nav>
</template>

<script>
export default {
    props:['current'],
    methods:{
        updateFilter(by){
            this.$emit('filterChange', by)
        }
    }
}
</script>

<style>
.filter-nav button{
    background: none;
    border: none;
    color: #bbb;
    outline: none;
    font-size: 12px;
    text-transform: uppercase;
    margin-right: 10px;
    letter-spacing: 1px;
    font-weight: bold;
    cursor: pointer;
}
.filter-nav button.active{
    color: #555;
}
</style>