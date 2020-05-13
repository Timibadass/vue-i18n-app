<template>
  <div>
    <h1>{{ $t("greetings") }}</h1>
    <p v-if="name.length > 0">{{ $t('hello', {name: name }) }}</p>
    <p>{{ $t('placeholder') }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloI18n",
  props: ["name"]
};
</script>

<i18n>
{
  "en": {
    "hello": "Hello, {name}, this is i18n in SFC!",
    "greetings": "Component Based Localization",
    "placeholder": "This is a component based fallback text"
  },
  "de": {}
}
</i18n>
