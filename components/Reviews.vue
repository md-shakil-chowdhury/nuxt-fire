<template>
    <div>
        <h3>Customer Reviews</h3>
        <!-- {{ $fetchState }} -->
        <div v-if="!$fetchState.pending">
           <ReviewCard  
                v-for="review in reviews.results"
                :key="review.login.uuid"
                :review="review"
           />
        </div>
        <div v-else>
            <h2>Loading...</h2>
        </div>
        
    </div>
</template>

<script>
    export default {
        data(){
            return{
                reviews:[]
            }
        },
        async fetch(){
            this.reviews = await fetch('https://randomuser.me/api/?results=5').then(res => res.json())
        }
        
    }
</script>

<style >
</style>