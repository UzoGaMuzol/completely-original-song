<template>
  <div>
    <div>
      <button class="btn btn-primary" @click="play">
        完全にオリジナルな音楽を{{ playOrStop }}
      </button>
    </div>
    <div>
    <select @change="osc.type=$event.target.value">
      <option
        v-for="sound in sounds"
        :value="sound"
        :key="sound"
      >
        {{ sound }}
      </option>
    </select>
    </div>
  </div>
</template>

<script>
import consts from "../../plugins/consts.js"

export default {
  data () {
    return {
      ctx: new AudioContext(),
      isPlaying: false,
      osc: null,
      timerId: null,
      sounds: consts.sounds
    }
  },
  computed: {
    playOrStop () {
      if (this.isPlaying) {
        return "停止"
      } else {
        return "再生"
      }
    }
  },
  methods: {
    play () {
      if (!this.isPlaying) {
        this.osc = this.ctx.createOscillator();
        this.osc.connect(this.ctx.destination)
        this.osc.start(0);
        this.changeFreqRandomly();
        this.isPlaying = true;
      } else {
        this.osc?.stop();
        clearTimeout(this.timerId);
        this.isPlaying = false;
      }
    },
    changeFreq (range) {
      if (this.isPlaying) {
        this.osc.frequency.value = Math.random() * range;
      }
    },
    changeFreqRandomly () {
      const time = Math.random() * consts.maxInterval;
      this.timerId = setTimeout(() => {
        this.changeFreq(consts.maxFreq);
        this.changeFreqRandomly();
      }, time)
    }
  }
}
</script>

<style>

</style>