<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单 / 易用 /便捷</h5>
    <translateForm v-on:formSubmit1="translate"></translateForm>
    <translateOutput :translateText="translateText"></translateOutput>
  </div>
</template>

<script>
  import translateForm from './components/translateForm'
  import translateOutput from './components/translateOutput'

export default {
  name: 'App',
  components: {
    translateForm,translateOutput
  },
  data:function(){
      return {
          translateText:""
      }

  },
  methods:{
    translate(text,lang){
        this.$http.get("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180924T105209Z.5fa427486e6eb06c.b6f98ebd389f9632b62b87ee503aaab6f648169f&lang="+lang+"&text="+text).then(res=>{
            this.translateText= res.body.text[0];
        })

    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
