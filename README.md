# Vue3 UUID

Add UUID to Vue instance.

[![Build Status](https://travis-ci.org/VitorLuizC/vue-uuid.svg?branch=master)](https://travis-ci.org/VitorLuizC/vue-uuid)

## Install

Installation is very easy, you just need to install using NPM or Yarn.

```sh
npm i vue3-uuid
```

Vue's `use` method will do the trick adding to Vue.

```js
import { createApp } from 'vue'
import App from './App.vue'
import UUID from "vue3-uuid";
const app = createApp(App)
app.use(UUID)

```

## Usage

After installation `$uuid` is available on instance, so you can use inside
components **template** and script, like the example below.

```vue
<template>
  <div class="uuid-panel">
    <h3 class="uuid">{{ UUID }}</h3>
    <button
      class="button"
      @click="choose"
    >Generate V1</button>
    <button
      class="button"
      @click="choose(3)"
    >Generate V3</button>
    <button
      class="button"
      @click="choose(4)"
    >Generate V4</button>
    <button
      class="button"
      @click="choose(5)"
    >Generate V5</button>
  </div>
</template>

<script setup>
  import { ref } from 'vue'
  import { uuid } from 'vue-uuid';
  const NAMESPACE = "65f9af5d-f23f-4065-ac85-da725569fdcd";

  const UUID = ref(null);

  const choose = ( type ) => {
    if ( type === 3 ) {
      UUID.value =  uuid.v3();
    } else if ( type === 4) {
      UUID.value = uuid.v4();
    } else if ( type === 5 ) {
      UUID.value = uuid.v5("Name 1", NAMESPACE);
    } else {
       UNID.value = uuid.v1();
    }
  }
</script>
```
