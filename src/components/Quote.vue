<template>
  <div class="card btn-light">
    <div class="card-body">
      <blockquote class="blockquote mb-0">
        <p>
          {{ quoteText }}
        </p>
      </blockquote>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quoteText: String
  }
};
</script>

<style lang="scss" scoped>
.card {
  margin: 10px;
  width: 31%;
  font-family: "Arizonia", cursive;
  transition: 0.3s;
  p {
    font-size: 26px;
  }
}
</style>
