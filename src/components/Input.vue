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
    <p class="helper-text">{{ helperText }}</p>
  </div>
</template>

<style scoped>
/* INPUT ICONS */
.input-icons {
  color: #828282;
  position: absolute;
  top: 38px;
}

.input-icon-start {
  left: 12px;
}
.input-icon-end {
  right: 73px;
}

.input-form:has(.input-icon-start) > input,
.input-form:has(.input-icon-start) > textarea {
  padding-left: 45px;
}

/* INPUT FORM */
.input-form {
  position: relative;
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

input,
textarea {
  width: 200px;

  border-radius: 8px;
  border: 1px solid #828282;
  padding: 12px 18px;
}

input.sm {
  height: 40px !important;
  padding: 10px 12px !important;
}
input.full {
  width: 100%;
}

input:hover,
textarea:hover {
  border: 1px solid #333333;
}

input:focus,
textarea:focus {
  border: 1px solid #2962ff;
  color: #2962ff;
  outline: none;
}

.input-error > label {
  color: #d32f2f;
}

.input-error > input {
  border: 1px solid #d32f2f;
}

.input-error:has(:hover) > label {
  color: #333333;
}
.input-error:has(:focus) > label {
  color: #2962ff;
}

.input-error > input:hover {
  border: 1px solid #333333;
}
.input-error > input:focus {
  border: 1px solid #2962ff;
}

.input-disabled > input {
  background-color: #f2f2f2;
  border: 1px solid #e0e0e0;
  color: #828282;
  pointer-events: none;
}

.input-disabled:has(:focus) > .input-label {
  color: #333333;
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
