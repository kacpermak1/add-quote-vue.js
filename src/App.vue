<template>
  <div class="container-fluid">
    <div class="container">
      <top-bar :quotesNumber="quotes.length"></top-bar>
      <div class="input-container">
        <app-input
          :addQuote="addQuote"
          :quotesNumber="quotes.length"
        ></app-input>
      </div>
      <div class="quote-list">
        <app-quote
          v-for="(quote, index) in quotes"
          :key="index"
          :quoteText="quote"
          @click.native="deleteQuote(index)"
        ></app-quote>
      </div>
      <app-bottom :quotesNumber="quotes.length"></app-bottom>
    </div>
  </div>
</template>

<script>
import TopBar from "./components/TopBar";
import Input from "./components/Input";
import Quote from "./components/Quote";
import BottomAlert from "./components/BottomAlert";

export default {
  data: function () {
    return {
      maxQuotes: 10,
      quotes: [],
    };
  },

  components: {
    "app-quote": Quote,
    "app-input": Input,
    "app-bottom": BottomAlert,
    "top-bar": TopBar,
  },
  methods: {
    addQuote(item) {
      this.quotes.push(item);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    },
  },
};
</script>

<style lang="scss" scoped>


.container {
  height: 100vh;
  overflow: scroll;
  -ms-overflow-style: none;
  &::-webkit-scrollbar {
    display: none;
  }
}
.quote-list {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  flex-wrap: wrap;
  margin-bottom: 30px;
}

.input-container {
  margin: 0 auto;
  width: 50%;
  margin-top: 30px;
  margin-bottom: 30px;
}
</style>
