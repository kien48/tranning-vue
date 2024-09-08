<script setup>
const msg = "hello world";
const rawHtml =
  '<div style="text-align:center"><p style="color:blue">Đây là html thô</p></div>';
const btnId = "btn-id";
const btnClass = "btn-class";
const isDisable = true;

const opject = {
  id: "btn-id-2",
  class: "btn-class-2",
  style: {
    color: "red",
  },
};

const number = 1;

const listString = "a,b,c,d,e,f";

const convertToId = (data) => data.split(",").join("+");

const attributeName = "href";
const url = "youtube.com";
</script>
<template>
  <h1>Syntax</h1>

  <p>Message : {{ msg }}</p>

  <p v-html="rawHtml"></p>

  <button :id="btnId" :class="btnClass" :disabled="isDisable">Button</button>

  <button v-bind="opject">Button 2</button>

  <button>Button 3: {{ number }}</button>

  <button :id="btnId" :class="btnClass" :disabled="isDisable">
    {{ isDisable ? "Disable" : "Button 1" }}
  </button>

  <button :id="listString.split(',').join('-')">Button 4</button>

  <button :id="convertToId(listString)">Button 5</button>

  <a v-bind:[attributeName]="url">Button 6</a>
</template>
