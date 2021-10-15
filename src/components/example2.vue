<template>
  <h3><code>Example 2: Show a hint for the focused field</code></h3>
  <div id="example2">
    <div><pre>{{ $data }}</pre></div>
    <p>
      <input type="text" v-focus="focused" @focus="focused = true" @blur="focused = false">
      <span v-if="focused">Focused!</span>
    </p>
  </div>
</template>

<script>
import {mixin} from '../focus.js';

export default {
  el: '#example2',
  mixins: [ mixin ],
  data () {
    return {
      focused: false,
    };
  },
};
</script>

<style>

</style>