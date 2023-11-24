<template>
  <div class="container-textcontent">
    <h1>INDONESIA</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores nostrum
      dignissimos reiciendis ratione aut, quae velit ullam repudiandae sunt
      impedit provident reprehenderit! Amet nisi quia dolorem, recusandae quae
      quis? Doloribus?
    </p>
    <button>
      <span>Explore</span>
      <svg
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M4 12H20M20 12L14 6M20 12L14 18"
          stroke="#fff"
          stroke-width="4"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </button>
  </div>
</template>

<style scope>
.container-textcontent {
  max-width: 500px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 20px;
  color: #fff;
  margin-left: 20px;
}

.container-textcontent h1 {
  font-size: 4.5em;
  font-weight: 900;
  letter-spacing: 5px;
}
.container-textcontent p {
  font-size: 1em;
}
.container-textcontent button {
  align-self: flex-start;
  background: #2b619f;
  border: 0;
  color: #fff;
  font-size: 1.3em;
  padding: 8px 25px;
  border-radius: 5px;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 15px;
  cursor: pointer;
}

@media screen and (max-width: 980px) {
  .container-textcontent {
    display: none;
  }
}
</style>
