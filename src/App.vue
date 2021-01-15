<template>
  <div id="app">
    <button @click="openModal">開く</button>
    <div id="overlay" v-if="show">
      <div id="content">
        <p>モーダルウインドウ</p>
        <button @click="closeModal">閉じる</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false
    };
  },
  methods: {
    openModal() {
      this.show = true;
    },
    closeModal() {
      this.show = false;
    }
  }
};
</script>

<style>
#overlay {
  z-index: 1;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}
#content {
  text-align: center;
  z-index: 2;
  width: 30%;
  padding: 10px;
  background: #fff;
}
</style>
