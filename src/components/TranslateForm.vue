<template>
  <div class="row" id="TranslateForm">
    <div class="col-md-5 col-md-offset-3">

    <form id="transForm" class="form-inline well" v-on:submit="formSubmit">
      <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word...">
      <select class="form-control" v-model="language">
        <option value="ru">Russian</option>
        <option value="es">Spanish</option>
        <option value="fr">French</option>
        <option value="zh">Chinese</option>
      </select>
      <input class="btn btn-primary" type="submit" value="translate">
    </form>
  </div>
  </div>
</template>

<script>

export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate:'',
      language:''
    }
  },
  created() {
    this.language = 'ru';
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>
  #transForm > * {
    margin: 0 5px;
  }
</style>
