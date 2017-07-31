<template>
  <div class="text-center" id="app">
    <h1>Yandex API Translator</h1>
    <h5>Powered by Vue.js</h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput.vue';

export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function(){
    return {
      translatedText:''
    }
  },
  methods: {
    translateText:function(text, language){
    this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170731T025949Z.1ecc411620214ed2.a2862b047c6c69315b43be1d3650b354f5484849&lang='+language+'&text='+text).then((response) => {
      // console.log(response.body.text[0])
      this.translatedText = response.body.text[0];
    });
    }
  }

}
</script>

<style>
body {
  background: #fefefe;
}
</style>
