<template>
<div style="margin: 30px">
  <Slider v-if="duration > 0" v-model="currentTime" :max="duration" :step="-1"/>
</div>

<button @click="playing = !playing">Play/pause</button>

<audio ref="audio" src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-16.mp3"/>
</template>

<script setup>
import Slider from '@vueform/slider'
import { ref } from 'vue'
import { useMediaControls } from '@vueuse/core'

const audio = ref(null)

const { playing, currentTime, duration } = useMediaControls(audio)
</script>