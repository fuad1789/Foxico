<template>
  <div class="container-leftbar">
    <div class="line">
      <div class="ball"></div>
      <div class="ball"></div>
      <div class="ball"></div>
      <div class="ball"></div>
    </div>
    <p>10 / 1</p>
  </div>
</template>

<style>
.container-leftbar {
  margin-left: 20px;
  margin-top: 30px;
}
.container-leftbar .line {
  width: 3px;
  height: 60vh;
  background-color: #ffffff73;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}
.container-leftbar .ball {
  width: 10px;
  height: 10px;
  border-radius: 30px;
  background: #ffffff;
}
.container-leftbar p {
  color: #fff;
  font-weight: 600;
  transform: rotateZ(-90deg);
  transform-origin: left;
  margin-top: 40px;
  white-space: nowrap;
}
</style>
