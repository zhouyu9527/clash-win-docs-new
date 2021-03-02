<template>
  <div class="question-answer">
    <h4 @click="isShow = !isShow">
      {{ question }}<span>{{ hint }}</span>
    </h4>
    <slot v-if="isShow" />
  </div>
</template>

<script>
export default {
  props: ["question"],
  data() {
    return {
      isShow: false,
    };
  },
  computed: {
    hint() {
      return this.isShow ? "隐藏解决方案" : "查看解决方案";
    },
  },
};
</script>

<style scoped>
.question-answer {
  border: 1px solid rgba(128, 128, 128, 0.205);
  padding: 0 20px;
  margin: 10px 0;
  border-radius: 5px;
}

h4 {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

span {
  font-size: 14px;
  color: rgb(57, 129, 223);
  margin-left: 20px;
  cursor: pointer;
}
</style>
