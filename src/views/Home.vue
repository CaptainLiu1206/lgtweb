<template>
    <div class="home">{{pagename}}</div>    
</template>
<script>
export default {
    name: 'Home',
    asyncData ({store, route}) {
    },
    title () {
        return 'home1'
    },
    data () {
        return {
            pagename: 'home page'
        }
    }
}
</script>
<style>

</style>
