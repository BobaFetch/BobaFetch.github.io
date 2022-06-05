<script>
  const src = 'images/placeholder.jpeg'
  let colorMode = 'light'
  export let view
</script>

<div class={`${colorMode} flex flex-col md:grid md:grid-cols-12 gap-1 h-screen py-5`}>

  <div class="md:col-span-6 mx-2">
    <div class="border border-slate-900 flex flex-col items-center py-2 rounded-lg bg-blue-100">
      <img src={src} width='100' height='100' class='rounded-full' />
      <h2 class='text-5xl'>ANDREW RIGGS</h2>
      <p>BUMBERSNATCH ENGINEER | SOME OTHER SHIT</p>
    </div>
  </div>

  <div class='md:col-span-6 mx-2'>
    <div class="border border-black p-2 rounded-lg">
      <h3 class='text-4xl'>ABOUT</h3>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </div>
  </div>
  <button on:click={() => view = 'retro'}>click me</button>
</div>

<style lang='postcss'>
  .dark {
    @apply 
      bg-slate-900
      text-gray-200;
  }

  .light {
    @apply
      bg-gray-100
      text-slate-900;
  }
</style>