<script lang="ts">
  import { Canvas } from '@threlte/core'
  import Scene from '$lib/components/Scene.svelte'
  import { turn } from '$lib/store'
</script>

<div class="h-screen" style="height: 100dvh;">
  <Canvas>
    <Scene />
  </Canvas>
  <div class="z-1 fixed top-4 left-4 bg-gray-200 shadow rounded px-2 py-1 flex items-center">
    <div class="w-4 h-4 rounded-full border border-black mr-1" style={`background-color: ${$turn == 1 ? 'black' : 'white'};`} />
    {$turn == 1 ? 'Black' : 'White'}
  </div>
</div>
