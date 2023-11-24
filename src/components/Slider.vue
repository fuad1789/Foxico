<template>
  <div class="slider-container">
    <div class="slider">
      <div
        v-for="(slide, i) in slides"
        :key="slide"
        :style="{
          backgroundImage: 'url(' + slide.img + ')',
          left: -active * 310 + 'px',
        }"
        class="slide"
        :class="{ active: i === active }"
        @click="goToSlide(i)"
      >
        <p>{{ slide.title }}</p>
        <span
          ><svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M5 7.8C5 6.11984 5 5.27976 5.32698 4.63803C5.6146 4.07354 6.07354 3.6146 6.63803 3.32698C7.27976 3 8.11984 3 9.8 3H14.2C15.8802 3 16.7202 3 17.362 3.32698C17.9265 3.6146 18.3854 4.07354 18.673 4.63803C19 5.27976 19 6.11984 19 7.8V21L12 17L5 21V7.8Z"
              stroke="black"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </span>
      </div>
    </div>
    <div class="slide-bottom-bar">
      <div class="arrow">
        <span style="padding-right: 3px" @click="moveSlider(-1)"
          ><svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M15 18L9 12L15 6"
              stroke="black"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </span>
        <span @click="moveSlider(1)"
          ><svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9 18L15 12L9 6"
              stroke="black"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import sliderPhto1 from "../assets/slider1.jpg";
import sliderPhto2 from "../assets/slider2.jpg";
import sliderPhto3 from "../assets/slider3.jpg";
import sliderPhto4 from "../assets/slider4.jpg";
import sliderPhto5 from "../assets/slider5.jpg";
import sliderPhto6 from "../assets/slider6.jpg";

export default {
  data() {
    return {
      slides: [
        {
          title: "Buddha tample, Thailand",
          img: sliderPhto1,
        },
        {
          title: "Broken beach, Bali",
          img: sliderPhto2,
        },
        {
          title: "Wat Arun, Bangkok",
          img: sliderPhto3,
        },
        {
          title: "Phi Phi Islands - Krabi",
          img: sliderPhto4,
        },
        {
          title: "Railay Beach - Krabi",
          img: sliderPhto5,
        },
        {
          title: "Grand Palace, Bangkok",
          img: sliderPhto6,
        },
      ],
      active: 0,
    };
  },
  methods: {
    moveSlider(direction) {
      const totalSlides = this.slides.length;
      this.active = (this.active + direction + totalSlides) % totalSlides;
    },
    goToSlide(index) {
      this.active = index;
    },
  },
};
</script>

<style scoped>
.slider-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  position: relative;
  margin-left: 60px;
  overflow: hidden;
}
.slider {
  width: 100%;
  height: 100%;
  display: flex;
  overflow: hidden;
  gap: 10px;
  align-items: center;
  position: relative;
}

.slide {
  flex: 0 0 auto;
  width: 300px;
  height: 75%;
  position: relative;
  transition: border 0.3s ease;
  transition: all 0.5s ease;
  background-position: center;
  background-size: cover;
  border-radius: 20px;
}
.slide p {
  position: absolute;
  top: -20px;
  font-weight: 700;
  color: #fff;
}
.slide span {
  position: absolute;
  background-color: #fff;
  top: 20px;
  right: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 7px;
  border-radius: 20px;
  -webkit-box-shadow: 0px 2px 38px -8px rgba(0, 0, 0, 0.69);
  -moz-box-shadow: 0px 2px 38px -8px rgba(0, 0, 0, 0.69);
  box-shadow: 0px 2px 38px -8px rgba(0, 0, 0, 0.69);
}

.slide.active {
  height: 90%;
}
.arrow {
  font-size: 1.1em;
  display: flex;
  gap: 10px;
  cursor: pointer;
}

.arrow span {
  width: 35px;
  height: 35px;
  background: #ffffff81;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 30px;
}

@media screen and (max-width: 980px) {
  .slider-container {
    margin-left: 30px;
  }
}
@media screen and (max-width: 460px) {
  .slider-container {
    margin-left: 0;
  }
  .slide {
    zoom: .86
  }
}
@media screen and (max-width: 380px) {
  .slider-container {
    margin-left: 0;
  }
  .slide {
    zoom: .7
  }
}
</style>
