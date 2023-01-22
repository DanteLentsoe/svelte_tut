<script>
  import { Palette } from '@untemps/svelte-palette'

  const colors = ['#865C54', '#8F5447', '#A65846', '#A9715E', '#AD8C72']

  let bgColor = colors[0]
</script>

<main class="flex align-center justify-center mt-48">
  <Palette
    {colors}
    allowDuplicates
    deletionMode="tooltip"
    on:select={({ detail: { color } }) => (bgColor = color)} />
</main>
