<template>
  <div class="wrapper">
    <h1>{{ x }}</h1>
    <a
      v-if="replaced"
      class="link"
      href="https://www.github.com/teziovsky"
      rel="nofollow noopener noreferrer"
      target="_blank">
      Click here to see my repo!
    </a>
    <button v-if="!replaced" class="btn" @click="replaceText">Replace!</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "HelloWorld",
  setup: () => {
    const x = ref("Hello world");
    const replaced = ref(false);

    const replaceText = () => {
      x.value = "Visit my Teziovsky GitHub account!";
      replaced.value = true;
    };

    return {
      x,
      replaced,
      replaceText,
    };
  },
});
</script>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 60px 0;
}

.link {
  text-decoration: none;
  margin-bottom: 20px;

  &:hover {
    text-decoration: underline;
  }

  &:focus {
    outline: 2px dashed #d1dbe5;
    outline-offset: 5px;
  }
}

.btn {
  cursor: pointer;
  width: 100px;
  font-size: 1rem;
  color: #d1dbe5;
  background-color: transparent;
  border: 2px solid #d1dbe5;
  padding: 6px 12px;

  &:hover {
    color: #2c3e50;
    background-color: #d1dbe5;
  }

  &:focus {
    outline: 2px dashed #d1dbe5;
    outline-offset: 5px;
  }
}
</style>
