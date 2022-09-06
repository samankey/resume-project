<template>
  <div class="grid">
    <div class="aaa">
      <div class="aa">
        <div class="first text" @click="() => isShow = !isShow">
          안녕2
        </div>
        <div class="second text">
          안녕2
        </div>
      </div>
    </div>
    <transition
      name="opacity"
      @enter="startTransition"
      @after-enter="endTransition"
      @before-leave="startTransition"
      @after-leave="endTransition"
    >
      <CompA v-if="isShow" class="comp" />
    </transition>
    <div class="bbb">
      <div class="third text" :class="{'active': isShow}">
        안녕3
      </div>
    </div>
  </div>
</template>

<script>
import CompA from '@/components/compA.vue'
export default {
  components: {
    CompA
  },

  data () {
    return {
      isShow: false
    }
  },

  methods: {
    startTransition (el) {
      el.style.height = el.scrollHeight + 'px';
    },
    endTransition (el) {
      el.style.height = '';
    }
  }
};
</script>

<style lang="scss" scoped>
.grid {
  height: 100vh;

  .aaa {
    display: grid;
    grid-template-rows: repeat(1, 8rem);
  
    .aa {
      display: flex;
      height: 10rem;
      z-index: -1;
    }
  }

  .bbb {
    display: grid;
    grid-template-rows: repeat(1, 8rem);
  }

  .comp {
    margin-top: 2rem;
  }
  .first {
    background: wheat;
    flex: 1;
    box-shadow: 0px -10px 15px rgba(48, 48, 48, 0.308);
  }

  .second {
    background: rgb(17, 138, 194);
    flex: 1;
    box-shadow: 0px -10px 15px rgba(48, 48, 48, 0.308);
  }

  .third {
    background: rgb(173, 17, 194);
    flex: 1;
    height: 10rem;
    box-shadow: 0px -10px 15px rgba(48, 48, 48, 0.308);
  }

  .text {
    padding: 1.5rem;
    font-size: 7rem;
    border-radius: 2rem 2rem 0 0;

    transition: ease-out 0.3s;
  }

  .active {
    transform: translateY(30rem);
  }
}

.opacity-enter-active, .opacity-leave-active {
  will-change: all;
  transition: all 0.2s ease;
}
.opacity-enter, .opacity-leave-to {
  height: 0 !important;
  padding: 0 !important;
  margin: 0 !important;
  opacity: 0 !important;
}
</style>