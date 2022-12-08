<template>
  <picture
    :class="{ loading: !imageLoaded }"
    :style="{ width: `${width || 50}px`, height: `${height || 50}px` }"
  >
    <img
      :src="src"
      :width="width || 50"
      :height="height || 50"
      @load="loaded"
    />
  </picture>
</template>
<script setup>
let { src } = defineProps(['src', 'width', 'height']);
</script>
<script>
export default {
  data() {
    return {
      imageLoaded: false,
    };
  },
  mounted() {
    this.$nextTick(() => {
      if (this.$refs.projImg?.$el.naturalWidth > 0) {
        this.imageLoaded = true;
      }
    });
  },
  methods: {
    loaded() {
      this.imageLoaded = true;
    },
  },
};
</script>
<style scoped>
picture {
  display: inline-block;
}
picture.loading {
  background-color: #0001;
  background-image: url(/images/loading.gif);
  background-size: cover;
}
</style>
