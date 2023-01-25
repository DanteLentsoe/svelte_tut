<script lang="ts">
  import Counter from './lib/Counter.svelte'
  import EyeDropper from './lib/Components/EyeDropper/index.svelte'
  import TailwindCss from './TailwindCSS.svelte'
  import Navigation from './lib/Navigation.svelte'
  import ImageUploader from './lib/Components/ImageUploader/index.svelte'
</script>

<style>

</style>

<div>

  <Navigation />
  <div class="flow-root ">
    <div class="float-left text-green-600">
      <ImageUploader />
    </div>
    <div class="float-right text-green-600">
      <EyeDropper />
    </div>

  </div>

  <TailwindCss />
</div>
