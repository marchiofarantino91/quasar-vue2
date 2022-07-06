<template>
  <q-page padding class="column flex-center">
    <div>
      <q-select
        v-model="multipleSelection"
        multiple
        label="Dog"
        style="min-width: 300px"
        use-input
        use-chips
        hide-dropdown-icon
        filled
        clearable
        @new-value="createValue"
      />
    </div>

    <pre>{{ multipleSelection }}</pre>
  </q-page>
</template>

<script setup>
import { ref } from 'vue';
import dogOptions from './dogOptions';

const selection = ref();
const multipleSelection = ref([]);

const loading = ref(false);

function createValue(newValue, done) {
  loading.value = true;
  done(newValue);
  // setTimeout(() => {
  //   loading.value = false
  // }, 1000)
}
</script>
