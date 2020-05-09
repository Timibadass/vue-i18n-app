<template>
  <div>
    <p>{{ $t('hello') }}</p>
    <p>{{ $t('greetings') }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloI18n"
};
</script>

<i18n>
{
  "en": {
    "hello": "Hello i18n in SFC!",
    "greetings": "Welcome to component"
  }
}
</i18n>
