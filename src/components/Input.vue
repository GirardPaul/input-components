<script setup>
import { ref } from "vue";

defineProps({
  label: {
    type: String,
    default: "Label",
  },
  placeholder: {
    type: String,
    default: "Placeholder",
  },
  error: {
    type: Boolean,
    default: false,
  },
  disabled: {
    type: Boolean,
    default: false,
  },
  helperText: String,
  startIcon: String,
  endIcon: String,
  value: String,
  size: {
    type: String,
    default: "md",
  },
  fullWidth: {
    type: Boolean,
    default: false,
  },
  multiline: {
    type: Boolean,
    default: false,
  },
  row: {
    type: Number,
    default: 4,
  },
});
</script>

<template>
  <div
    :class="[
      'input-form',
      { 'input-error': error, 'input-disabled': disabled },
    ]"
  >
    <label class="input-label">{{ label }}</label>

    <div :class="['input-wrapper', { full: fullWidth }]">
      <i v-if="startIcon" class="material-icons input-icon-start input-icons">{{
        startIcon
      }}</i>
      <input
        type="text"
        :placeholder="placeholder"
        :value="value"
        :class="[size, fullWidth ? 'full' : '']"
        v-if="!multiline"
      />
      <textarea
        v-else
        :placeholder="placeholder"
        :value="value"
        :rows="row"
        :class="[size, fullWidth ? 'full' : '']"
      />

      <i v-if="endIcon" class="material-icons input-icon-end input-icons">{{
        endIcon
      }}</i>
    </div>

    <p class="helper-text">{{ helperText }}</p>
  </div>
</template>

<style scoped>
input,
textarea {
  border: none;
  outline: none;
}
input:hover,
textarea:hover {
  border: none;
  outline: none;
}
input:focus,
textarea:focus {
  border: none;
  outline: none;
}

/* INPUT ICONS */
.input-icons {
  color: #828282;
}

.input-icon-start {
  margin-left: 12px;
}
.input-icon-end {
  margin-right: 12px;
}

/* INPUT FORM */
.input-form {
  display: flex;
  flex-direction: column;
}

/* INPUT */

input {
  height: 56px;
}

textarea {
  resize: none;
}

.input-wrapper {
  width: 200px;
  display: flex;
  align-items: center;
  border-radius: 8px;
  border: 1px solid #828282;
}

input,
textarea {
  border: none;
  outline: none;
  flex-grow: 1;
  border-radius: 8px;
  padding: 12px 18px;
  width: 100%;
}

input.sm {
  height: 40px !important;
  padding: 10px 12px !important;
}
.full {
  width: 100% !important;
}

.input-wrapper:hover {
  border: 1px solid #333333;
}

.input-wrapper:focus,
.input-wrapper:focus-within {
  border: 1px solid #2962ff;
  color: #2962ff;
  outline: none;
}

.input-error > label {
  color: #d32f2f;
}

.input-error > .input-wrapper {
  border: 1px solid #d32f2f;
}

.input-error:has(:hover) > label {
  color: #333333;
}
.input-error:has(:focus) > label {
  color: #2962ff;
}

.input-error > .input-wrapper:hover {
  border: 1px solid #333333;
}
.input-error > .input-wrapper:focus,
.input-error > .input-wrapper:focus-within {
  border: 1px solid #2962ff;
}

.input-disabled > .input-wrapper {
  background-color: #f2f2f2;
  border: 1px solid #e0e0e0;
  color: #828282;
  pointer-events: none;
}

.input-disabled:has(:focus) > .input-label {
  color: #333333;
}

.input-disabled > .input-wrapper {
  border: 1px solid #e0e0e0 !important;
}
.input-disabled > .input-wrapper > input,
.input-disabled > .input-wrapper > textarea {
  background: #f2f2f2 !important;
}

/* LABEL */

.input-label {
  font-size: 12px;
  font-weight: 400;
  margin-bottom: 4px;
  color: #333333;
}

.input-form:has(:focus) > label {
  color: #2962ff;
}

/* HELPER TEXT */

.helper-text {
  font-size: 10px;
  font-weight: 400;
  color: #828282;
  margin-top: 4px;
}

.input-error > .helper-text {
  color: #d32f2f;
}

.input-form:has(:hover) > .helper-text {
  color: #333333;
}
.input-form:has(:focus) > .helper-text {
  color: #2962ff;
}
</style>
