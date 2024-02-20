<script setup>
import { ref } from "vue";
const value = ref("Mohammed Faizan");
const lazyModifier = ref("");
const numberModifier = ref();
const trimModifier = ref("");
const message = ref("");
const checked = ref(false);
const checkedNames = ref([]);
const picked = ref("one")
const selected = ref("")
const MultiSelected = ref([])

</script>

<template>
  <div>
    <h1>V-model Example</h1>
    <input type="text" v-model="value" style="margin-bottom: 10px" />
    <br />
    <p>{{ value }}</p>
    <br />
    <h1>V-model lazy modifier Example</h1>

    <input
      type="text"
      v-model.lazy="lazyModifier"
      style="margin-bottom: 10px"
    />
    <br />
    <p>{{ lazyModifier }}</p>
    <br />
    <h1>V-model number modifier Example</h1>

    <input
      type="number"
      v-model.number="numberModifier"
      style="margin-bottom: 10px"
    />
    <br />
    <p>{{ numberModifier }}</p>
    <br />
    <h1>V-model trim modifier example</h1>
    <input
      type="text"
      v-model.trim="trimModifier"
      style="margin-bottom: 10px"
    />
    <br />
    <p>{{ trimModifier }}</p>
    <br />
    <h2>Multiline example</h2>
    <br />

    <textarea v-model="message" placeholder="add multiple lines"></textarea>
    <br />
    <span>Multiline message is:</span>
    <p style="white-space: pre-line">{{ message }}</p>
    <br />
    <h2>Checkbox example</h2>
    <input type="checkbox" id="checkbox" v-model="checked" />
    <label for="checkbox">{{  checked }}</label>
    <br />
    <h2>Multiple Checkbox example </h2>
    <div>Checked names: {{ checkedNames }}</div>

    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
    <label for="jack">Jack</label>

    <input type="checkbox" id="john" value="John" v-model="checkedNames" />
    <label for="john">John</label>

    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
    <label for="mike">Mike</label>
    <br>

    <h2>Radio Buttons example</h2>

    <div>Picked: {{ picked }}</div>

    <input type="radio" id="one" value="One" v-model="picked" />
    <label for="one">One</label>

    <input type="radio" id="two" value="Two" v-model="picked" />
    <label for="two">Two</label>
    <br>
    <h2>Select example</h2>
    <br>
    <div>Selected: {{ selected }}</div>

    <select v-model="selected">
      <option disabled value="">Please select one</option>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <br>
    <h2>Multi Select</h2>
    <br>
    <div>Selected: {{ MultiSelected }}</div>

    <select v-model="MultiSelected" multiple>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <br> 
  </div>

</template>

<style scoped>
body {
  background: #eff8ff;
  height: 100vh;
  width: 100vw;
  font-family: system-ui, BlinkMacSystemFont, -apple-system, Segoe UI, Roboto,
    Oxygen, Ubuntu, Cantarell, Fira Sans, Droid Sans, Helvetica Neue, sans-serif;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0;
  padding: 0;
}
</style>
