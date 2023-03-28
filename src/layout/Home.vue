<script setup>
import Sidebar from "../components/Sidebar.vue";
import Input from "../components/Input.vue";
import { ref } from "vue";

const inputDefault = ref("<Input />");
const inputError = ref("<Input error />");
const inputDisabled = ref("<Input disabled />");
const inputHelperText = ref('<Input helperText="Some interesting text" />');
const inputHelperTextError = ref(
  '<Input helperText="Some interesting text" error />'
);
const inputStartIcon = ref("<Input startIcon />");
const inputEndIcon = ref("<Input endIcon />");
const inputWithValue = ref('<Input value="text" />');
const inputSizeSm = ref('<Input size="sm" />');
const inputSizeMd = ref('<Input size="md" />');
const inputFullWidth = ref("<Input fullWidth />");
const inputTextArea = ref('<Input multiline row="4" />');
</script>

<template>
  <div class="flex">
    <Sidebar />
    <div class="full flex flex-column buttons-container">
      <h3>Inputs</h3>
      <div class="flex flex-wrap">
        <div class="col">
          <p>{{ inputDefault }}</p>
          <Input />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="col">
          <p>{{ inputError }}</p>
          <Input error />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="col">
          <p>{{ inputDisabled }}</p>
          <Input disabled />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="col">
          <p>{{ inputHelperText }}</p>
          <Input helperText="Some interesting text" />
        </div>
        <div class="col">
          <p>{{ inputHelperTextError }}</p>
          <Input helperText="Some interesting text" error />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="col">
          <p>{{ inputStartIcon }}</p>
          <Input startIcon="call" />
        </div>
        <div class="col">
          <p>{{ inputEndIcon }}</p>
          <Input endIcon="lock" />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="col">
          <p>{{ inputWithValue }}</p>
          <Input value="Text" />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="col">
          <p>{{ inputSizeSm }}</p>
          <Input size="sm" />
        </div>
        <div class="col">
          <p>{{ inputSizeMd }}</p>
          <Input size="md" />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="full">
          <p>{{ inputFullWidth }}</p>
          <Input fullWidth />
        </div>
      </div>
      <div class="flex flex-wrap mt-45">
        <div class="col">
          <p>{{ inputTextArea }}</p>
          <Input multiline row="4" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
p {
  font-size: 12px;
  font-weight: 400;
}
.mt-45 {
  margin-top: 45px;
}
.full {
  width: 100%;
}
.col {
  flex: 0 0 auto;
}
.buttons-container {
  padding: 50px 82px;
}
h3 {
  font-weight: 500;
  font-size: 24px;
}
.flex {
  display: flex;
}
.flex-wrap {
  flex-wrap: wrap;
}
.flex-column {
  flex-direction: column;
}

@media screen and (min-width: 992px) {
  .col {
    width: 25% !important;
  }
}
@media screen and (max-width: 991px) {
  .col {
    width: 50% !important;
  }
}
@media screen and (max-width: 767px) {
  .col {
    width: 100% !important;
  }
}
</style>
