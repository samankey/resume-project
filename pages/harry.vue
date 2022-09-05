<template>
  <div class="grid">
    <div class="aa">
      <div class="first text" @click="() => isShow = !isShow">
        안녕2
      </div>
      <div class="second text">
        안녕2
      </div>
    </div>
    <transition
      name="accordion-item"
      @enter="startTransition"
      @after-enter="endTransition"
      @before-leave="startTransition"
      @after-leave="endTransition"
    >
      <CompA v-if="isShow" />
    </transition>
    <div class="third text" :class="{'active': isShow}">
      안녕3
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
  }
};
</script>

<style lang="scss" scoped>
.grid {
  display: grid;
  grid-template-rows: repeat(3, 10rem);
  height: 100vh;

  .aa {
    display: flex;
    height: 10rem;
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

    transition: ease-out 0.2s;
  }

  .active {
    transform: translateY(30rem);
  }
}

/* .accordion-item-enter-active, .accordion-item-leave-active {
  will-change: all;
  transition: all 0.2s ease;
}
.accordion-item-enter, .accordion-item-leave-to {
  height: 0 !important;
  padding: 0 !important;
  margin: 0 !important;
  opacity: 0 !important;
} */
</style>