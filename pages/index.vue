<template>
  <div>
    <div class="flex">
      <div class="first text" @click="bb">
        테스트
      </div>
      <div class="second text" @click="() => isShowShow = !isShowShow">
        테스트
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
    <transition
      name="accordion-item"
      @enter="startTransition"
      @after-enter="endTransition"
      @before-leave="startTransition"
      @after-leave="endTransition"
    >
      <CompB v-if="isShowShow" />
    </transition>
    <div class="third text">안녕</div>
  </div>
</template>

<script>
import CompA from '@/components/compA.vue'
import CompB from '@/components/compB.vue'
export default {
  components: {
    CompA, CompB
  },

  data () {
    return {
      isShow: false,
      isShowShow: false
    }
  },

  methods: {
    bb () {
      this.isShow = !this.isShow;
    }
  }
}
</script>

<style lang="scss" scoped>
.flex {
  display: flex;
  width: 100%;

}
.first {
  background: wheat;
  flex: 1;
}

.second {
  background: rgb(17, 138, 194);
  flex: 1;
}

.third {
  background: rgb(173, 17, 194);
  flex: 1;
}

.text {
  padding: 1.5rem;
  font-size: 8rem;
}
.accordion-item-enter-active, .accordion-item-leave-active {
  will-change: all;
  transition: all 0.2s ease;
}
.accordion-item-enter, .accordion-item-leave-to {
  height: 0 !important;
  padding: 0 !important;
  margin: 0 !important;
  opacity: 0 !important;
}
</style>