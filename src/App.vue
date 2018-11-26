<template>
    <div>
        <project-list :projectId="projectId" @projectClicked="changeId"></project-list>
        <scatter-plot :projectId="projectId"></scatter-plot>
    </div>
</template>

<script>
    import ProjectList from './components/project-list';
    import ScatterPlot from './components/scatter-plot';
    export default {
        name: 'app',
        components: {
            ProjectList,
            ScatterPlot
        },
        data() {
            return {
                projectId: ''
            }
        },
        methods: {
            changeId: function(id) {
                this.projectId = id
            }
        }
    }
</script>

<style lang="scss">
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }
    body {
        padding: 20px;
    }
</style>
