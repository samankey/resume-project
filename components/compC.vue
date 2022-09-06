<template>
  <div class="absol">
    <div class="flex" :class="isShow ? 'bo' : ''">
      <div class="text aa" @click="() => isShow = !isShow">
        apple
      </div>
      <div class="text bb">
        banana
      </div>
    </div>
    <div class="text cc" :class="isShow ? 'toptop' : 'top'">
      mango
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
    }
  },

  methods: {

  }
};
</script>

<style lang="scss" scoped>
.absol {
  position: relative;
  display : table;
  flex: 1;

  .flex {
    position: absolute;
    display: flex;;
    width: 100%;
  }

  .text {
    padding: 0.75rem;
    font-size: 3rem;
    transition: ease-out 0.3s;
    border: 5px solid #040608;
    cursor: url('@/assets/images/backhand1.png'), pointer;
  }

  .aa {
    background: #c44a44;
    flex: 1;
    border-right: none;
  }

  .bb {
    background: #8ea48e;
    flex: 1;
  }

  .cc {
    width: 100%;
    position: absolute;
    background: #0b3761;
    flex: 1;
  }

  .top {
    top: 3.7rem
  }

  .toptop {
    top: 30rem
  }
}
</style>