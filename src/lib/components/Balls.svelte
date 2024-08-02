<script lang="ts">
  import { T } from '@threlte/core'
  import { state } from '$lib/store'
</script>

{#each { length: 4 } as _, x}
  {#each { length: 4 } as _, y}
    {#each { length: 4 } as _, z}
      {#if $state[x][y][z]}
        <T.Mesh position={[x * 10 + 5 - 20, y * 9 + 5 - 19, z * 10 + 5 - 20]}>
          <T.SphereGeometry args={[4.5]} />
          <T.MeshStandardMaterial color={['black', 'white'][$state[x][y][z] - 1]} />
        </T.Mesh>
      {/if}
    {/each}
  {/each}
{/each}
