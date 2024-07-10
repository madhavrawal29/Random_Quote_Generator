<script setup>
import { quotes } from "./data";
import { ref } from "vue";

const randomQuote = ref(quotes[1]);

const randomQuoteHandler = () => {
  randomQuote.value = quotes[Math.floor(Math.random() * quotes.length)];
};
</script>

<template>
  <div class="main-wrapper">
    <h1>Random Quote Generator</h1>

    <blockquote class="quote-wrapper">
      <p>{{ randomQuote.quote }}</p>
      <cite>{{ randomQuote.author }}</cite>
    </blockquote>
    <button @click="randomQuoteHandler" class="btn">Change Quote</button>
  </div>
</template>

<style scoped>
.main-wrapper {
  position: relative;
  top: 30%;
  text-align: center;
  padding: 24px 70px;
  background: rgb(212, 163, 163);
  border-radius: 15px;

  h1 {
    font-family: times, Times New Roman, times-roman, georgia, serif;
    color: #000000;
    margin: 0;
    padding: 10px;
    font-size: 40px;
    letter-spacing: -2px;
    font-weight: bold;
  }
  .quote-wrapper {
    padding: 10px;
    border: 1px solid gray;
    border-radius: 5px;
    padding: 50px 20px;
    p {
      font-size: 20px;
      color: brown;
      font-family: system-ui;
      font-weight: 600;
    }
    cite {
      color: dimgray;
      font-size: 24px;
      padding: 10px 0;
    }
  }
  .btn {
    cursor: pointer;
    outline: 0;
    display: inline-block;
    font-weight: 400;
    line-height: 1.5;
    text-align: center;
    background-color: #0f91b5;
    border: 1px solid transparent;
    padding: 15px 70px;
    font-size: 20px;
    border-radius: 0.25rem;
    transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
      border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
    color: #fff;
    border-color: #0f91b5;
    margin: 20px 0;
  }
  .btn:hover {
    color: #0f91b5;
    background-color: transparent;
    border-color: #0f91b5;
  }
}
</style>
