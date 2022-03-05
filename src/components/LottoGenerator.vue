<template>
    <div class="container">
        <img src="../assets/pcso.png" alt="lotto-logo">
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
    margin-right: 150px;
}
img{
    height: 130px;
    padding: 10px;
}

button{
    margin-bottom: 10px;
    margin-left: 550px;
    font-size: 20px;
    
}

.output {
    padding: 10px;
    font-weight: bold;
    font-size: 20px;
    margin-left: 120px;
    

}

</style>