<script setup lang="ts">
defineProps<{
  clicked: Object;
}>();
</script>

<template>
  <div class="card">
    <div v-if="!clicked.value">
      <div class="line">
        <label for="website">On which website</label>
        <input
          id="website"
          class="text"
          type="website"
          placeholder="a website to remember"
          label="Wich website"
        />
      </div>
      <div class="line">
        <label for="website">My login</label>
        <input class="text" type="text" placeholder="login" />
      </div>
      <div class="line">
        <label for="website">My password</label>
        <input class="text" type="password" placeholder="password" />
      </div>
    </div>
    <div v-else>
      <img
        src="../assets/risk.svg"
        class="warnlogo"
        alt="Never do this again"
      />
      <h1>Never do this again</h1>
      <p class="read-the-docs">
        Don't give your identifiers to any random websites
      </p>
    </div>
    <button
      class="savebutton"
      type="button"
      @click="clicked.value = !clicked.value"
    >
      {{ clicked.value ? "Reset" : "Save it now" }}
    </button>
  </div>

  <p class="read-the-docs">Keep important things within reach</p>
  <p class="read-the-docs">Your security is our priority</p>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
}
.line {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  vertical-align: center;
  align-content: center;
  line-height: 50px;
}
.text {
  margin: 10px 0;
  height: 30px;
  line-height: 30px;
  width: 70%;
}
.text:hover,
.savebutton:hover {
  filter: drop-shadow(0 0 1em #646cffaa);
}
.read-the-docs {
  color: #888;
}
.warnlogo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
</style>
