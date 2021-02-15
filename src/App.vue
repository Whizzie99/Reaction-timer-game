<template>
  <div>
    <h1 class="main-header animate__animated animate__shakeX">How fast are you?⚡</h1>

  <div class="tips animate__animated animate__backInLeft">
    <h4>Rating</h4>
    <p>Your rating is based on how fast you respond to the <b>click me</b> block 😉</p>
    <ul>
      <li>Very Fast⚡⚡ - oshey Flash! 🥵</li>
      <li>Fast⚡ - Ya doing well 😉</li>
      <li>Slow🐌 - Lori Iro! You too slow abeg 🙄</li>
    </ul>
  </div>

  <p class="fun-msg animate__animated animate__backInLeft">Have fun playing!!🤪</p>

  <button class="animate__animated animate__bounceInUp" @click="start" :disabled="isPlaying">{{ btnText }}</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :score="score"/>
  <Footer/>
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
import Footer from './components/Footer.vue'
export default {
  name: 'App',
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      btnText: 'Play ▶️'
    }
  },
  components:{
    Block,
    Results,
    Footer
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying =true
      this.showResults = false
    },

    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
      this.btnText = 'play again 🔁'
    }
  }
}
</script>

<style>
:root{
  --gradient: linear-gradient(to right, #ff416c, #ff4b2b);
  --webkit-gradient: -webkit-linear-gradient(to right, #ff416c, #ff4b2b);
}


#app {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  /* margin-top: 60px; */
  height: 100vh;
}

.main-header{
  font-family: 'Reggae One', cursive;
}

.tips{
  font-family: cursive;
}

.tips h4{
  margin: 0;
}

.tips p{
  margin: 0;
}

.tips p b{
  font-size: 1.1em;
}

.tips ul li{
  list-style: none;
}


button{
  /* background: #0faf87; */
  color: #fff;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  font-family: cursive;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
  width: 200px;
  background-size: 300% 100%;
  background-image: var(--webkit-gradient);
  background-image: var(--gradient);

  -moz-transition: all .4s ease-in-out;
  -o-transition: all .4s ease-in-out;
  -webkit-transition: all .4s ease-in-out;
  transition: all .4s ease-in-out;



}

button:hover{
  background-position: 100% 0;
  -moz-transition: all .4s ease-in-out;
  -o-transition: all .4s ease-in-out;
  -webkit-transition: all .4s ease-in-out;
  transition: all .4s ease-in-out;
}

button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}

.fun-msg{
  font-weight: bold;
  font-size: 1.1em;
  margin: 20px 0;
}
</style>
