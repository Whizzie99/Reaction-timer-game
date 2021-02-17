<template>
    <footer>
        <p class="animate__animated animate__bounceInUp"> For fun &copy; {{ date }}. <a :href="mylink" target="_blank">Wisdom Obioma</a></p>
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
        width: 100%;
        display: flex;
        justify-content: center;
        font-family: 'Architects Daughter', cursive;
    }

    footer p{
        text-align: center;
    }

    footer a{
        text-decoration: none;
        color: #ff4b2b;
    }
</style>