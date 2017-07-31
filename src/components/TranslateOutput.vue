<template>
  <h2 class="text-primary">{{translatedText}}</h2>
</template>

<script>

export default {
  name: 'translateOutput',
  props:['translatedText'],
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate);
      e.preventDefault();
    }
  }
}
</script>

<style>

</style>
