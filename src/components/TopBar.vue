<template>
  <div>
    <h2>Quotes added</h2>
    <div class="load-bar alert-secondary progress">
      <p class="initial-counter" v-if="!quotesNumber">{{ quotesNumber }}/10</p>
      <div
        class="load-bar-color alert-success progress-bar"
        aria-valuemin="0"
        v-bind:style="{ width: quotesNumber * 10 + '%' }"
      >
        <p v-if="quotesNumber">{{ quotesNumber }}/10</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {};
  },

  props: {
    quotesNumber: Number,
  },
};
</script>

<style lang="scss" scoped>
.load-bar {
  width: 100%;
  height: 40px;
  display: flex;
    align-items: center;
    justify-content: flex-start;
    position:relative;
  .load-bar-color {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  p {
    text-align: center;
    margin: 5px;
    font-size: 18px;

    &.initial-counter{
        position:absolute;
        left:5px;
        top:0;
        bottom:0;
    }
  }
}
</style>
