<template>
  <div class="d-grid gap-2">
    <button type="button" class="btn btn-primary" @click="onClick()">
      Submit Value
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/composition-api";

export default defineComponent({
  props: {
    value: {
      type: String,
      required: true
    }
  },
  setup(props) {
    const onClick = () => {
      window.alert(props.value);
    };

    return { onClick };
  }
});
</script>
