<template>
    <div>
        <h1>My Items</h1>
        <MyItem  
            v-for="item in myRentals"
            :key="item.id"
            :item="item"
        />
    </div>
</template>

<script>
import {mapState} from "vuex"
    export default {
        layout:"no-nav",
        computed:{
            ...mapState(['myRentals'])
        }
    }
</script>

<style  scoped>

</style>