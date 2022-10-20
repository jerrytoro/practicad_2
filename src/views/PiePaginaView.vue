<template>
    <div>
        <footer :style="footerColor">
        </footer>
    </div>
</template>

<script>
export default {
    name: 'piePaginaView',
    data() {
        return {
            footerColor: "background-color:slategrey",
        }
    },
    methods: {
    },
    computed: {
    },
    mounted() {
    },
    components: {
    }
}
</script>

<style>
footer {

    text-align: center;
    padding: 30px 10px;
    margin-top: 50px;
    min-height: 100px;
}
</style>