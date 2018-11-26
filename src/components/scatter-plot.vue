<template>
    <div>Chosen project id: <span v-if='projectId'>{{projectId}}</span></div>
</template>

<script>
    export default {
        name: 'ScatterPlot',
        props: ['projectId']
    }
</script>

<style lang="scss">
</style>
