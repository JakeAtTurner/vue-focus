<template>
  <h3><code>Example 4: Custom label</code></h3>
  <div id="example4">
    <div><pre>{{ $data }}</pre></div>
    <p>
      <span role="label" @mousedown.prevent="focused = true">Label</span>
      <input type="text"
        v-focus="focused"
        @focus="focused = true"
        @blur="focused = false"
      >
    </p>
    <p>NOTE: click on the label to focus the input.</p>
  </div>
</template>

<script>
import {mixin} from '../focus.js';
export default {
  el: '#example4',
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