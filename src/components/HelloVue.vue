<template>
  <div>
    <p>Hello {{ name }}, I am a Vue component</p>
  </div>
</template>

<script>
export default {
  name: "HelloVue",
  props: {
    name: String
  }
};
</script>