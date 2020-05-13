<template>
  <div class="home">
    <h1>{{ $t("greetings") }}</h1>
    <p>{{ $t("summary") }}</p>
    <button>
      <router-link to="/formatting">{{ $t("start") }}</router-link>
    </button>
  </div>
</template>

<script>
export default {
  name: "home"
};
</script>
