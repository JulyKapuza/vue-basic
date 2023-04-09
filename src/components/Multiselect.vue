<template>
 <div>
      <label class="typo__label">Single select</label>
      <multiselect class="mult" v-model="value" :custom-label="nameWithLang" :options="options" :searchable="false" :close-on-select="false" :show-labels="false" placeholder="Pick a value"></multiselect>
      <pre class="language-json"><code>{{ value }}</code></pre>
    </div>
</template>

<script setup >
import Multiselect from 'vue-multiselect'
import { ref } from 'vue';
const value = ref("Select option");
const options =  [ 'options', 'selected', 'multiple', 'label', 'searchable', 'clearOnSelect', 'hideSelected', 'maxHeight', 'allowEmpty', 'showLabels', 'onChange', 'touched']

const nameWithLang = function nameWithLang(options) {
  return `${options}`
    }

</script>
<style >


.mult .multiselect__element{
  color:rgb(140, 199, 44) !important;
}

.mult .multiselect__option--selected.multiselect__option--highlight {
    background: #34aca2;
    color: #0f5699;
}
</style>