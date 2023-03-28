<script setup></script>

<template>
  <div class="main">
    <p><span class="text-red">Dev</span>challenges.io</p>

    <ul>
      <li>
        <a href="#">Typography</a>
      </li>
      <li>
        <a href="#">Grid</a>
      </li>
      <li>
        <a href="#">Buttons</a>
      </li>
      <li>
        <a href="#" class="active">Inputs</a>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.main {
  background-color: #fafbfd;
  padding: 40px;
  color: #090f31;
  width: 250px;
  display: flex;
  flex-direction: column;
}

a {
  text-decoration: none;
  color: #9e9e9e;
}

/* a active */
.active {
  color: #090f31;
  font-weight: 700;
}

ul {
  padding: 0;
}

li:first-of-type {
  padding-top: 112px !important;
}

li {
  list-style: none;
  padding: 17.5px 0px;
  font-weight: 500;
  font-size: 14px;
}

p,
span {
  font-weight: 600;
  font-size: 13px;
}

.text-red {
  color: #f7542e;
}
</style>
