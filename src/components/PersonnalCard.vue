<template>
  <div id="person-card">
    <h3>{{ user.name }}</h3>
    <div class="data"><strong>E-mail:</strong> {{ user.email }}</div>
    <!-- <div class="data"><strong>Phone:</strong> {{ user.phone }}</div> -->
    <div class="data"><strong>City:</strong> {{ user.city }}</div>
    <div class="data"><strong>Languages:</strong> {{ user.lang }}</div>
    <div class="data">
      <strong>
        <a
          href="https://drive.google.com/file/d/1Ejw7RMa2BDfGet7BgMQBXz9DJl2zTM00/view?usp=sharing"
          target="_blank"
        >
          <u>Resume</u>
        </a>
      </strong>
    </div>
    <SocialBar :links="links" />
  </div>
</template>

<script>
import SocialBar from "./SocialBar.vue";

export default {
  name: "PersonnalCard",
  props: ["user", "links"],
  components: {
    SocialBar
  }
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

#person-card {
  color: lighten(map-get($colors, light), 100%);
}

.data {
  margin-bottom: 15px;
}
</style>
