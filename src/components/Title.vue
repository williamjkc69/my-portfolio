<template>
  <div class="title" :class="isSkill ? 'title-light' : 'title-primary'">
    <h2>{{ title }}</h2>
    <div class="wrapper">
      <div class="text-wrapper">{{ description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Title",
  props: ["title", "description", "isSkill"]
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

.title {
  text-align: center;
  h2 {
    font-size: 4rem;
    text-transform: uppercase;
  }
}
.title-light{
  color: map-get($colors, light);
}
.title-primary{
  color: map-get($colors, primary);
}

.text-wrapper {
  text-transform: uppercase;
  &:after {
    content: "";
    width: 150px;
    display: block;
    margin: 20px auto;
    border-bottom: 1px solid map-get($colors, primary);
  }
}
</style>
