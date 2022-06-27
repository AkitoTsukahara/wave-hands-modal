<template>
  <div class="message" @click="clickHand(noActivated)">
    Hello there!
    <div :class="{ wave: noActivated }">
      <span class="hand">👋</span>
    </div>
  </div>
</template>

<script>

export default {
  name: 'wave-hands',
  data() {
    return {
      noActivated: false,
      interval: null,
    };
  },
  methods: {
    clickHand() {
      if (this.noActivated === true || this.interval !== null) {
        return;
      }
      this.noActivated = true;
      this.interval = setInterval(() => {
        this.noActivated = false;
        clearInterval(this.interval);
        this.interval = null;
      }, 2000);

    },
  },
};
</script>
<style scoped lang="scss">
.message {
  display: flex;
  cursor: pointer;
  font-size: 32px;
}

.hand {
  font-size: 32px;
}

.wave {
  animation-name: waving-hand;
  animation-duration: 2s;
  animation-direction: normal;
  animation-timing-function: ease;
  transform: scale(1, 1);
}

@keyframes waving-hand {
  0% {
    transform: rotate(0deg);
  }
  10% {
    transform: rotate(14deg);
  }
  20% {
    transform: rotate(-8deg);
  }
  30% {
    transform: rotate(14deg);
  }
  40% {
    transform: rotate(-4.0deg);
  }
  50% {
    transform: rotate(10deg);
  }
  60% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

</style>
