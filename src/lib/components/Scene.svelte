<script lang="ts">
  import { T } from '@threlte/core'
  import { OrbitControls } from '@threlte/extras'
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

<T.Mesh position.y={-20.5}>
  <T.BoxGeometry args={[40, 1, 40]} />
  <T.MeshStandardMaterial color="#8b4513" />
</T.Mesh>

{#each { length: 4 } as _, i}
  {#each { length: 4 } as _, j}
    <T.Mesh position={[i * 10 + 5 - 20, 0, j * 10 + 5 - 20]}>
      <T.CylinderGeometry args={[0.75, 0.75, 40]} />
      <T.MeshStandardMaterial color="white" />
    </T.Mesh>
  {/each}
{/each}
