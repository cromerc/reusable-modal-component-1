<script setup>
import { XMarkIcon } from "@heroicons/vue/20/solid";

const props = defineProps({
  title: { type: String, default: "" },
});

const emit = defineEmits(["close"]);

function close() {
  emit("close");
}
</script>

<template>
  <div class="modal-wrapper">
    <div class="modal-wrapper-inner">
      <button class="modal-close-button" @click="close()">
        <XMarkIcon class="w-8 h-8" />
      </button>
      <div class="modal-title">
        {{ props.title }}
      </div>
      <div class="modal-inner">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
