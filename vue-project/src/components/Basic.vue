<script setup>
import { reactive, ref } from "vue";

const counter = reactive({ count: 20 });
const msg = ref("Привіт, світе!");
const text = ref("Підкреслений текст");
const titleClass = ref("title");
const subtitleClass = ref("subtitle");
const isButtonDisabled = true;
const isPromoted = true;
const isSoldOut = true;
const isSold = false;
const styleObject = {
    color: "orchid",
    fontSize: "50px",
    padding: "20px",
};
const baseStyleObj = {
    fontSize: "50px",
    padding: "10px",
};
const successStyleObj = {
    color: "blueviolet",
    backgroundColor: "violet",
    border: "1px solid blueviolet",
};
const warningStyleObj = {
    color: "#0e6b66",
    backgroundColor: "lightseagreen",
    border: "1px solid #0e6b66",
};
</script>

<template>
    <div>
        <h1 :class="titleClass">{{ msg }}</h1>
        <h2 class="underline">{{ text }}</h2>
        <h3 :class="isPromoted && 'promoted'">Текст курсивом за умови</h3>
        <p :class="subtitleClass">Рахунок: {{ counter.count }}</p>
        <h3 :class="isSoldOut ? 'sold-out' : 'new'">Продано фільми?</h3>
        <!-- декілька класів можна прописувати в масив і також зазначати умову -->
        <h3 :class="[isPromoted && 'promoted', isSold ? 'sold-out' : 'new']">
            Продано фільми?
        </h3>
        <!--зaстосування стилів об'єкт  -->
        <h3 :class="{
            promoted: isPromoted,
            new: !isSold,
            'sold-out': isSold,
        }">
            Object conditinal movie
        </h3>
        <button :disabled="isButtonDisabled">Bind</button>
        <h3 :style="styleObject">Style Object</h3>
        <!-- Останній об'єкт має пріоритет коли є конфліктні стилі -->
        <div :style="[baseStyleObj, successStyleObj]">Success Style</div>
        <div :style="[baseStyleObj, warningStyleObj]">Warning Style</div>
    </div>
</template>

<style scoped>
.title {
    color: aqua;
}

.subtitle {
    color: cadetblue;
}

.underline {
    text-decoration: underline;
}

.promoted {
    font-style: italic;
    /* color: #0e6b66 */
}

.new {
    color: lawngreen;
}

.sold-out {
    color: orangered;
}
</style>
