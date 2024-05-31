<template>
  <div class="calc-container">
    <div class="equation" id="equation">{{ equationElement }}</div>
    <button class="calc-btn clear" @click="Clear()">AC</button>
    <button
      class="calc-btn divide fa-solid fa-divide"
      @click="Operation('/')"
    />
    <button class="calc-btn one fa-solid fa-1" @click="Operation('1')" />
    <button class="calc-btn two fa-solid fa-2" @click="Operation('2')" />
    <button class="calc-btn three fa-solid fa-3" @click="Operation('3')" />
    <button
      class="calc-btn multiply fa-solid fa-xmark"
      @click="Operation('*')"
    />
    <button class="calc-btn four fa-solid fa-4" @click="Operation('4')" />
    <button class="calc-btn five fa-solid fa-5" @click="Operation('5')" />
    <button class="calc-btn six fa-solid fa-6" @click="Operation('6')" />
    <button class="calc-btn minus fa-solid fa-minus" @click="Operation('-')" />
    <button class="calc-btn seven fa-solid fa-7" @click="Operation('7')" />
    <button class="calc-btn eight fa-solid fa-8" @click="Operation('8')" />
    <button class="calc-btn nine fa-solid fa-9" @click="Operation('9')" />
    <button class="calc-btn plus fa-solid fa-plus" @click="Operation('+')" />
    <button class="calc-btn zero fa-solid fa-0" @click="Operation('0')" />
    <button
      class="calc-btn decimal fa-solid fa-circle"
      @click="Operation('.')"
    />
    <button class="calc-btn equal fa-solid fa-equals" @click="Equal()" />
  </div>
</template>

<script setup>
import { ref } from "vue";

const equationElement = ref("");
const setEquationElement = (newValue) => {
  equationElement.value = newValue;
};

function Operation(e) {
  let equation = e;
  console.log(equation);
  setEquationElement(equationElement.value + equation);
  console.log(equationElement);
}
function Equal() {
  setEquationElement(eval(equationElement.value));
}
function Clear() {
  setEquationElement("");
}
</script>
