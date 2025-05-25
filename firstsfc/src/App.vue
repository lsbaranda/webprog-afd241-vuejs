<template>
  <h1>Hello World!</h1>
  <h1>Food</h1>
  <food-item/>

</template>

<script setup>
import { ref, onMounted } from 'vue'
import { supabase } from './lib/supabaseClient'

const instruments = ref([])

async function getInstruments() {
  const { data } = await supabase.from('instruments').select()
  instruments.value = data
}

onMounted(() => {
   getInstruments()
})
</script>

<style>
</style>