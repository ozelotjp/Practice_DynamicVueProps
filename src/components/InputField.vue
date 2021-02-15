<template>
  <div>
    <label for="field" class="form-label">Value</label>
    <div class="input-group">
      <input
        id="field"
        class="form-control"
        type="text"
        name="field"
        placeholder="ABC..."
        required
        v-model="field"
        @input="execEmit()"
        @change="execEmit()"
      />
      <button
        class="btn btn-outline-secondary"
        type="button"
        @click="insertRandomValue()"
      >
        Random Value
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "@vue/composition-api";

export default defineComponent({
  setup(_, { emit }) {
    const field = ref("");

    const execEmit = () => {
      emit("update:value", field.value);
    };

    const insertRandomValue = () => {
      field.value = Math.random()
        .toString(32)
        .substring(2);
      execEmit();
    };

    return { field, execEmit, insertRandomValue };
  }
});
</script>
