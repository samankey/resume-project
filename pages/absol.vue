<template>
  <div class="flefle">
    <div class="qq">
      Hi, This is Samankey.<br>
      Thank you.<br>
      <br>
      I'm front-end developer.
    </div>
    <CompC />
  </div>
</template>

<script>
import CompC from '@/components/compC.vue'
export default {
  components: {
    CompC
  },

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
.flefle {
  display: flex;
  height: 100%;

  .qq {
    padding: 5.5rem;
    flex: 0.75;
    height: 100%;
    background-color: #040608;
    color: white;
  }
}

@media screen and (max-width:500px) {
  .flefle {
    display: block;
  }
}
</style>