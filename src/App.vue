<template>
  <div id="app">
    <div>
      <button @click="translate('Мальчик', 'ru', 'en')">Перевести!</button>
    </div>
  </div>
</template>

<script>
import translate from 'google-translate-open-api';
export default {
  name: 'App',
  methods: {
   async translate(value, fromLanguage, toLanguage) {
      const result = await translate(value, {
        from: fromLanguage,
        to: toLanguage,
        browers: true
      });
      const data = result.data[0];
     console.log(data);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
