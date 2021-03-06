<template>
  <div class="list">
    <template v-for="(ad, index) in ads">
      <lazy-img :src="ad.img" class="item" @click="handleAdClick(ad)" />
      <div v-if="index < ads.length - 1" class="saperator"></div>
    </template>
  </div>
</template>

<script>
import LazyImg from "./lazy-img.vue";

export default {
  components: { LazyImg },
  data() {
    return {
      ads: [
        {
          url: "https://aaex.uk/cart.php?language=chinese",
          img: "https://api.crhnode.top/banner.png",
        },
        {
          url: "https://jike138.net/auth/register?code=LdON",
          img: "https://sy168.site/tupian/clash.jpg",
        },
        {
          url: "https://fastlink.ws/auth/register?code=clashw",
          img: "http://download.fastlink.ws/fastlink_banner.jpg",
        },
        {
          url: "http://cylink.wtf",
          img: "http://to.kache.moe/ad/clash_690_150.jpeg",
        },
      ],
    };
  },
  methods: {
    handleAdClick({ url }) {
      if (url) {
        window.open(url);
      }
    },
  },
};
</script>

<style scoped>
.list {
  margin: 10px 0;
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
}

.item {
  max-height: 150px;
  max-width: 690px;
}

.saperator {
  height: 2px;
  width: 100%;
  background-color: #f1f1f1;
  margin: 5px 0;
}
</style>
