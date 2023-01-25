<script lang="ts">
  let avatar: string | ArrayBuffer, fileinput

  const onFileSelected = (e: { target: EventTarget & HTMLInputElement }) => {
    let image = e.target.files[0]
    let reader = new FileReader()
    reader.readAsDataURL(image)
    reader.onload = (e) => {
      avatar = e.target.result
    }
  }

  $: console.log('avatar', avatar)
</script>

<style>
  #app {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-flow: column;
  }

  .upload {
    display: flex;
    height: 50px;
    width: 50px;
    cursor: pointer;
  }

  .avatar:hover {
    cursor: pointer;
  }
  .avatar {
    display: flex;
    height: 350px;
    width: 350px;
  }
</style>

<div id="app">
  <h1>Upload Image</h1>

  {#if avatar}
    <img class="avatar" src={typeof avatar === 'string' && avatar} alt="d" />
  {:else}
    <img
      class="avatar"
      src="https://cdn4.iconfinder.com/data/icons/small-n-flat/24/user-alt-512.png"
      on:click={() => {
        fileinput.click()
      }}
      alt="" />
  {/if}
  <img
    class="upload"
    src="https://static.thenounproject.com/png/625182-200.png"
    alt=""
    on:click={() => {
      fileinput.click()
    }} />
  <div
    class="chan"
    on:click={() => {
      fileinput.click()
    }}>
    Choose Image
  </div>
  <h2>Clear Image</h2>
  <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
    on:click={() => {
      avatar = null
    }}>
    Clear
  </button>
  <input
    style="display:none"
    type="file"
    accept=".jpg, .jpeg, .png"
    on:change={(e) => onFileSelected(e)}
    bind:this={fileinput} />

</div>
