<script lang="ts">
  import { T } from '@threlte/core'
  import { state, turn } from '$lib/store'

  const colors = [
    [0, 0, 0, 0],
    [0, 0, 0, 0],
    [0, 0, 0, 0],
    [0, 0, 0, 0],
  ]

  const addBall = (x: number, z: number) => {
    for (let y = 0; y < 4; y++) {
      if ($state[x][y][z] == 0) {
        $state[x][y][z] = $turn
        $turn = $turn == 1 ? 2 : 1
        break
      }
    }
  }
</script>

{#each { length: 4 } as _, x}
  {#each { length: 4 } as _, z}
    <T.Mesh
      position={[x * 10 + 5 - 20, 0, z * 10 + 5 - 20]}
      on:click={() => addBall(x, z)}
      on:pointerenter={() => colors[x][z] = 1}
      on:pointerleave={() => colors[x][z] = 0}
    >
      <T.CylinderGeometry args={[1, 1, 38]} />
      <T.MeshStandardMaterial color={['#deb887', '#ff0000'][colors[x][z]]} />
    </T.Mesh>
  {/each}
{/each}
