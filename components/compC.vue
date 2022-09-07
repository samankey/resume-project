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
    <div class="absol2" :class="isShow ? 'toptop' : 'top'">
      <div class="absol3">
        <div class="cc text" @click="() => isShowShow = !isShowShow">
          mango
        </div>
        <div class="text ee" :class="isShowShow ? 'toptop' : 'top'">
          갸갸
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
      isShowShow: false
    }
  },

  methods: {

  }
};
</script>

<style lang="scss" scoped>
.absol {
  position: relative;
  flex: 1;
  overflow: auto;

  .flex {
    position: absolute;
    display: flex;;
    width: 100%;
  }

  .text {
    padding: 0.75rem;
    font-size: 3rem;
    transition: all 250ms cubic-bezier(0.125, 0.550, 0.805, 0.440); /* custom */
    transition-timing-function: cubic-bezier(0.125, 0.550, 0.805, 0.440); /* custom */
    border: 5px solid #040608;
    cursor: url('@/assets/images/backhand1.png'), pointer;
  }

  .absol2 {
    position: absolute;
    width: 100%;
    transition: all 250ms cubic-bezier(0.125, 0.550, 0.805, 0.440); /* custom */
    transition-timing-function: cubic-bezier(0.125, 0.550, 0.805, 0.440); /* custom */

    .absol3 {
      position: relative;

      .cc {
        position: absolute;
        width: 100%;
        background: #0b3761;
        flex: 1;
      }

      .ee {
        width: 100%;
        position: absolute;
        background: #c1d897;
      }
    }

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

  .top {
    top: 3.7rem
  }

  .toptop {
    top: 30rem
  }
}

@media screen and (max-width:500px) {
  .absol {
    overflow: visible;
  }
}
</style>