<template>
  <div
    class="container-mobilemenu"
    :style="[isActiveMenu ? { right: '30px' } : { right: '-300px' }]"
  >
  
    <div class="links-mobilemenu">
      <h4>Hello , Anney</h4>
      <p>News</p>
      <p>Destinations</p>
      <p>Blog</p>
      <p>Contact</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isActiveMenu: Boolean,
  },
};
</script>

<style>
.container-mobilemenu {
  min-width: 200px;
  position: absolute;
  top: 90px;
  right: 30px;
  background-color: #fff;
  border-radius: 20px;
  overflow: hidden;
  transition: all 500ms ease-in-out;
}

.links-mobilemenu {
  color: #292929;
  font-weight: 500;
  display: flex;
  flex-direction: column;
}

.links-mobilemenu p {
  padding: 10px 0;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 300ms;
}

.links-mobilemenu p:hover {
  background: #292929;
  color: #fff;
}

.links-mobilemenu h4 {
  text-align: center;
  padding: 10px 0;
  border-bottom: 1px solid #292929;
}

</style>
