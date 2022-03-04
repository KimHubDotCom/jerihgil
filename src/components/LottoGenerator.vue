<template>
    <div class="container">
        <img src="../assets/logo.png" alt="lotto-logo">
        <h1>My Lotto Generator</h1>
    </div>
    <button @click="generate()">Generate Numbers</button>
    <div class="container">
        <div class="output" v-for="digit in randomDigits" :key="digit">
            {{ digit }}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            randomDigits : [],
            isPlaying : false
        }
    },
    methods: {
        generate(){

            while(this.randomDigits.length < 6){
                let digits = Math.floor((Math.random() * 41)) + 1;
                if(!this.randomDigits.includes(digits)){
                    this.randomDigits.push(digits);
                }
            }
        }
    }
}
</script>

<style scoped>
.container{
    display: flex;
    align-items: center;
    justify-content: center;
}
img{
    height: 60px;
    padding: 5px;
}

button{
    margin-bottom: 10px;
    margin-left: 885px;
}

.output {
    padding: 5px;
    font-weight: bold;
}

</style>
You sent
<template>
  <LottoGenerator/>
</template>

<script>
import LottoGenerator from './components/LottoGenerator.vue'
export default {
  name: 'App',
  components: {
    LottoGenerator,
  }
}
</script>

<style>
#LottoGeneratorapp {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>