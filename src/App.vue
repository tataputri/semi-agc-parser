<script>
import { ref } from 'vue';

export default {
  data() {
    return {
      keyword: '',
      html: '',
    };
  },
  setup() {
    const count = ref(0);

    // expose to template and other options API hooks
    return {
      keyword: '',
      count,
    };
  },
  methods: {
    openBing() {
      window.open(
        'https://www.bing.com/images/async?q=' +
          encodeURIComponent(this.keyword)
      );
      console.log(this.keyword);
    },
    sendData() {},
  },

  mounted() {
    console.log(this.count); // 0
  },
};
</script>

<template>
  <div>
    <input type="text" name="keyword" id="keyword" v-model="keyword" />
    <button @click="openBing">STEP 1</button>
    <textarea name="" id="" cols="30" rows="10" v-model="html"></textarea>
    <button @click="sendData">PROCESS</button>
  </div>
</template>

<style scoped></style>

<style scoped></style>
