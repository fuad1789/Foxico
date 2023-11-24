<template>
  <div
    class="container-searchbox"
    :class="isActive && 'active'"
    @click="openInput"
  >
    <Teleport to="#app">
      <div class="closebox" v-if="isActive" @click="closeInput" />
    </Teleport>
    <svg
      style="pointer-events: none"
      width="24"
      height="24"
      viewBox="0 0 24 24"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M21 21L16.65 16.65M11 6C13.7614 6 16 8.23858 16 11M19 11C19 15.4183 15.4183 19 11 19C6.58172 19 3 15.4183 3 11C3 6.58172 6.58172 3 11 3C15.4183 3 19 6.58172 19 11Z"
        stroke="#4D4D4D"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <input
      ref="input"
      v-bind:style="[isActive ? { width: '100px' } : { width: '0' }]"
      placeholder="Search..."
      type="text"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },

  methods: {
    openInput() {
      if (window.innerWidth > 500) {
        this.isActive = true;
        this.$refs.input.focus();
      }else{
        this.$router.push("/search")
      }
    },
    closeInput() {
      this.isActive = false;
    },
  },
};
</script>

<style scoped>
.container-searchbox {
  background: #fff;
  min-width: 35px;
  min-height: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 20px;
  cursor: pointer;
  transition: all 500ms;
}

.active {
  border-radius: 20px;
  padding: 0 10px;
  gap: 7px;
}

.container-searchbox input {
  border: 0;
  font-size: 0.9em;
  outline: none;
  font-weight: 500;
  transition: all 500ms;
  z-index: 100;
}
.closebox {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
