<template>
  <div class="home">
    <!-- <HelloI18n /> -->
    <h1>{{ $t("greetings") }}</h1>
    <p>{{ $t("summary") }}</p>
    <button>
      <router-link to="/formatting">{{ $t("start") }}</router-link>
    </button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloI18n from "@/components/HelloI18n.vue";

export default {
  name: "home",
  components: {
    HelloI18n
  }
};
</script>
