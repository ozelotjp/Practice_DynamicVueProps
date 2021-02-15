<template>
  <div id="app" class="container">
    <h1 class="mt-3">Practice_DynamicVueProps</h1>
    <form>
      <input-field class="mt-3" :value.sync="field" />
      <submit-button class="mt-3" :value="field" />
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "@vue/composition-api";
import InputField from "@/components/InputField.vue";
import SubmitButton from "@/components/SubmitButton.vue";

export default defineComponent({
  components: {
    InputField,
    SubmitButton
  },
  setup() {
    const field = ref("");

    return { field };
  }
});
</script>
