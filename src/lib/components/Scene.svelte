<script lang="ts">
  import { T } from '@threlte/core'
  import { interactivity, OrbitControls } from '@threlte/extras'
  import Polls from '$lib/components/Polls.svelte'
  import Balls from '$lib/components/Balls.svelte'

  interactivity({
    filter: (hits, state) => {
      return hits.slice(0, 1)
    }
  })
</script>

<T.PerspectiveCamera
  makeDefault
  position={[0, 0, 150]}
>
  <OrbitControls
    enableDamping
  />
</T.PerspectiveCamera>

<T.DirectionalLight position={[0, 60, 30]} />
<T.AmbientLight />

<T.Mesh position.y={-19} on:click={() => {}} on:pointerenter={() => {}} on:pointerleave={() => {}}>
  <T.BoxGeometry args={[40, 1, 40]} />
  <T.MeshStandardMaterial color="#8b4513" />
</T.Mesh>

<Polls />

<Balls />
