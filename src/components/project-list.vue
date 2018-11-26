<template>
    <ul id="ProjectList">
        <li @click="chooseProject(key)" v-for="(value, key) in projects" :key="key">{{ value }}</li>
    </ul>
</template>

<script>
    export default {
        name: 'ProjectList',
        data: function () {
            return {
                projects: JSON.parse(this.getData())
            };
        },
        methods: {
            getData: function () {
                const request = new XMLHttpRequest();
                request.open('GET', './src/assets/data.json', false);
                request.send();
                if (request.status !== 200) {
                    console.log(request.status + ' : ' + request.statusText);
                } else {
                    return request.responseText;
                }
            },
            chooseProject: function (key) {
                this.$emit('projectClicked', key);
            }
        }
    }
</script>

<style lang="scss">
    ul {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        list-style: none;
        margin: 0 0 15px;

        li {
            margin: 5px 0;
            text-decoration: underline;
            cursor: pointer;

            &:hover {
                text-decoration: none;
            }

        }

    }
</style>
