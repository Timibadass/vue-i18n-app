<template>
  <section>
    <h1>{{$t('formattingTitle')}}</h1>
    <p v-show="showMessage">{{ $t('hello', {name: name}) }}</p>
    <form @submit.prevent="showMessage = true">
      <label for="name">{{ $t('name') }}</label>
      <input type="text" name="name" id="name" v-model="name" />
      <input type="submit" :disabled="name.length < 1" value="send" />
      <label for="hideMessage" v-if="showMessage">
        <input type="checkbox" name="hideMessage" id="hideMessage" v-model="showMessage" /> Show Message
      </label>
    </form>
    <!-- div element -->
    <div v-html="$t('htmlText')"></div>
    <button @click="switchLocale">Switch to {{locale}}</button>
    <div>
      <h1>{{ $t('fallbackLocale') }}</h1>
      <p>{{ $t('placeholder', 'de') }}</p>
      <p>{{ $tc('developer', 0) }}</p>
      <p>{{ $tc('developer', 1) }}</p>
      <p>{{ $tc('developer', 2) }}</p>
    </div>
    <HelloI18n :name="name" />
  </section>
</template>

<script>
// @ is an alias to /src
import HelloI18n from "@/components/HelloI18n.vue";
export default {
  data() {
    return {
      name: "",
      showMessage: false,
      locale: "Deutsch"
    };
  },
  components: {
    HelloI18n
  },
  methods: {
    switchLocale() {
      this.$i18n.locale = this.locale === "English" ? "en" : "de";
      this.locale = this.$i18n.locale === "en" ? "Deutsch" : "English";
    }
  }
};
</script>

<style>
form {
  width: 100%;
  max-width: 300px;
  margin: 20px auto;
}

label {
  display: block;
  width: 100%;
  text-align: left;
  margin-bottom: 5px;
}

input[type="text"] {
  width: 100%;
  height: 30px;
  border-radius: 3px;
  border: 1px solid #eee;
  padding-left: 10px;
  box-sizing: border-box;
  margin-bottom: 10px;
}

input[type="submit"] {
  width: 80px;
  height: 30px;
  border-radius: 3px;
  border: 0;
}
</style>