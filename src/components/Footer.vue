<template>
    <footer>
        <p class="animate__animated animate__bounceInUp">Built for fun &copy; {{ date }}. <a :href="mylink" target="_blank">Wisdom Obioma</a></p>
    </footer>
</template>

<script>
export default {
    data(){
        return{
            date: new Date().getFullYear(),
            mylink: 'https://github.com/Whizzie99'
        }
    }

}
</script>

<style>
    footer{
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        display: flex;
        justify-content: center;
        font-family: cursive;
    }

    footer p{
        text-align: center;
    }

    footer a{
        text-decoration: none;
        color: #ff4b2b;
    }
</style>