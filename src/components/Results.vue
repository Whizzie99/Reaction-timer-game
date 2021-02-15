<template>
    <p class="animate__animated animate__fadeIn">Reaction Time - {{ score }} ms </p>
    <p class="rank animate__animated animate__bounceIn">{{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return{
            rank: null
        }
    },
    mounted(){
        if(this.score < 250){
            this.rank = "Toh Sharp! 🥵"
        }else if(this.score < 400){
            this.rank = "Ya doing well! 😉"
        } else{
            this.rank = "Lori Iro! You too slow abeg 🙄" 
        }
    }
}
</script>

<style>
    p{
        font-family: cursive;
    }

    .rank{
        font-size: 1.4em;
        color: #ff4b2b;
        font-weight: bold;
    }
</style>