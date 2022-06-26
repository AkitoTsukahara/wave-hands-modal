<template>
  <div class="wave-hands">
    <WaveHands/>
  </div>
</template>

<script>
import WaveHands from '@/components/waveHands';

export default {
  name: 'App',
  components: {
    WaveHands,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.wave-hands {
  position: absolute;
  bottom: 50px;
  right: 50px;
}
</style>
