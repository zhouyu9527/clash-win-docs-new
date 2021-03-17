<template>
  <div class="lazy-img">
    <div v-show="isDefault" class="card pending">
      <div>Clash for Windows</div>
    </div>
    <img
      v-show="isLoaded"
      class="img"
      @load="imgLoaded"
      @error="imgFailed"
      :src="src"
      @click="$emit('click')"
    />
    <div v-show="isFailed" class="card failed">
      <div>image 404</div>
    </div>
  </div>
</template>

<script>
const DEFAULT_STATUS = Symbol();
const LOADED_STATUS = Symbol();
const FAILED_STATUS = Symbol();

export default {
  props: ["src"],
  data() {
    return {
      status: DEFAULT_STATUS,
    };
  },
  computed: {
    isDefault() {
      return this.status === DEFAULT_STATUS;
    },
    isLoaded() {
      return this.status === LOADED_STATUS;
    },
    isFailed() {
      return this.status === FAILED_STATUS;
    },
  },
  methods: {
    imgLoaded() {
      this.status = LOADED_STATUS;
    },
    imgFailed() {
      this.status = FAILED_STATUS;
    },
  },
};
</script>

<style scoped>
.lazy-img {
  width: 690px;
  height: 150px;
}

.card {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(128, 128, 128, 0.233);
}

.pending {
  color: rgb(170, 170, 170);
}

.failed {
  color: rgba(196, 38, 38, 0.719);
}

.img {
  cursor: pointer;
}
</style>
