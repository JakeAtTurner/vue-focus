<template>
  <h3><code>Example 1: Autofocus</code></h3>
  <div id="example1">
    <p><label><input type="checkbox" v-model="shown"> Show the field</label></p>
    <p v-if="shown"><input type="text" v-focus.lazy="true"></p>
    <p>NOTE: field is focused from the start, and gains focus whenever it enters the DOM.</p>
  </div>
</template>

<script>
import {mixin} from '../focus.js';
console.log(mixin);
export default {
  el: '#example1',
  mixins: [ mixin ],
  data () {
    return {
      shown: true,
    };
  },
};
</script>

<style>

</style>