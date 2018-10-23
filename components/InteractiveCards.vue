<template>
  <div class="card-wpr">
    <div
      v-for="(card, i) in cards"
      :key="i"
      :class="currentCard === i ? 'active' : 'inactive'"
      class="card"
    >
      <div class="number-bg"></div>
      <div class="number">{{i + 1}}</div>
      <div class="text">
        <span class="headline">{{card.title}}</span>
        <p>{{card.text}}</p>
      </div>
      <button @click="nextCard">OK</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "InteractiveCards",
  data() {
    return {
      currentCard: 0
    };
  },
  props: {
    cards: {
      type: Array,
      default() {
        return [
          {
            title: "The couch",
            text: "If you want to grow, get outside your comfort zone."
          },
          {
            title: "Failing is learning",
            text: "Pick yourself up, dust yourself off, and start again."
          },
          {
            title: "Flowers and rainbows",
            text: "Always be yourself, unless you can be a unicorn."
          }
        ];
      }
    }
  },
  methods: {
    nextCard() {
      this.currentCard = (this.currentCard + 1) % 3;
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Open+Sans:600,400");
.card-wpr {
  position: relative;
  min-width: 240px;
  min-height: 150px;
  font-family: "Open Sans", Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.card {
  position: absolute;
  z-index: 0;
  width: 100%;
  height: 100%;
  background: #fff;
  box-shadow: -4px 6px 16px 4px rgba(0, 0, 0, 0.1);
  border-radius: 3px;
  overflow: hidden;
  pointer-events: none;
  opacity: 0;
  -webkit-transform: scale(0.5);
  transform: scale(0.5);
}
.card.active {
  pointer-events: all;
  z-index: 1;
  -webkit-animation: fadeIn 0.6s ease-in-out both 0.5s;
  animation: fadeIn 0.6s ease-in-out both 0.5s;
}
.card.inactive {
  z-index: 2;
  -webkit-animation: fadeOut 0.5s ease-in-out both;
  animation: fadeOut 0.5s ease-in-out both;
}
.card .number-bg {
  position: absolute;
  width: 60px;
  height: 60px;
  top: -31px;
  right: -31px;
  background: #8391a1;
  -webkit-transform: rotate(45deg);
  transform: rotate(45deg);
}
.card .number {
  position: absolute;
  top: 6px;
  right: 8px;
  font-size: 13px;
  line-height: 13px;
  font-weight: 600;
  color: #fff;
}
.card .text {
  text-align: center;
  padding: 20px 10px;
}
.card .text .headline {
  display: block;
  font-size: 14px;
  line-height: 22px;
  font-weight: 600;
  color: #616e7d;
  margin-bottom: 8px;
}
.card .text p {
  font-size: 12px;
  line-height: 17px;
  color: #8391a1;
  max-width: 200px;
  margin: 0 auto;
}
.card button {
  position: absolute;
  width: 100%;
  height: 40px;
  bottom: 0;
  left: 0;
  right: 0;
  background: #3ca7fb;
  cursor: pointer;
  text-align: center;
  text-transform: uppercase;
  line-height: 38px;
  font-size: 13px;
  transition: all 0.3s ease-in-out;
  border: none;
  color: #fff;
}
.card button:hover,
.card button:focus {
  outline: 0;
  background: #2196f3;
}

@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
    -webkit-transform: scale(0.9);
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    -webkit-transform: scale(0.9);
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
    -webkit-transform: scale(1);
    transform: scale(1);
  }
  to {
    opacity: 0;
    -webkit-transform: scale(1.15);
    transform: scale(1.15);
  }
}
@keyframes fadeOut {
  from {
    opacity: 1;
    -webkit-transform: scale(1);
    transform: scale(1);
  }
  to {
    opacity: 0;
    -webkit-transform: scale(1.15);
    transform: scale(1.15);
  }
}
</style>
