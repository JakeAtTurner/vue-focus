<template>
  <h3><code>Example 3: Move focus</code></h3>
  <div id="example3">
    <div><pre>{{ { focused: focused } }}</pre></div>
    <p v-for="(item, index) in items" v-bind:key="index">
      <input type="text"
         v-model="item.value"
         @keydown.down.prevent="moveDown"
         @keydown.up.prevent="moveUp"
         v-focus="index === focused"
         @focus="focused = index"
         @blur="focused = null"
       >
    </p>
    <p>NOTE: move the focus with ↑ and ↓ keys.</p>
  </div>
</template>

<script>
import {mixin} from '../focus.js';
export default {
  el: '#example3',
  mixins: [ mixin ],
  data () {
    return {
      focused: null,
      items: [
        { value: 'hello' },
        { value: 'world' },
        { value: '' },
        { value: 'hello' },
        { value: 'world' },
        { value: '' },
      ],
    };
  },
  methods: {
    moveDown: function() {
      this.focused = Math.min(this.focused + 1, this.items.length - 1);
    },
    moveUp: function() {
      this.focused = Math.max(this.focused - 1, 0);
    },
  },
};
</script>

<style>

</style>