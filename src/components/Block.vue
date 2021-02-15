<template>
    <div class="block animate__animated animate__bounceIn" v-if="showBlock" @click="stopTimer">
        Click Me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted(){
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },
    methods:{
        startTimer(){
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        
        stopTimer(){
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    }
}
</script>

<style>
:root{
    --gradient: linear-gradient(to right, #ff416c, #ff4b2b);
    --webkit-gradient: -webkit-linear-gradient(to right, #ff416c, #ff4b2b);
}


.block{
    width: 400px;
    border-radius: 20px;
    color: #fff;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    font-family: cursive;
    background-size: 300% 100%;
    background-image: var(--webkit-gradient);
    background-image: var(--gradient);

    -moz-transition: all .4s ease-in-out;
    -o-transition: all .4s ease-in-out;
    -webkit-transition: all .4s ease-in-out;
    transition: all .4s ease-in-out;
}

.block:hover{
    background-position: 100% 0;
    -moz-transition: all .4s ease-in-out;
    -o-transition: all .4s ease-in-out;
    -webkit-transition: all .4s ease-in-out;
    transition: all .4s ease-in-out;
}
</style>