<script lang="ts">
  import TailwindCss from "./TailwindCSS.svelte";
  import Header from './lib/components/Header.svelte'
  import About from './lib/components/About.svelte'
  import Stack from './lib/components/Stack.svelte'
  import NormalView from "./lib/components/NormalView.svelte";

  const componentMap = {
    About,
    Stack
  }

  let commandTxt:string
  let help:boolean = false
  let errorMsg:string

  let Display
  let view:string = 'retro'

  function handleKeyPress(e) {
    if (e.keyCode === 13) {
      errorMsg = null
      Display = null
      help = false
      switch (commandTxt) {
        case 'help':
        case '-help':
        case '-h':
          help = true
          commandTxt = ''
          break;
        
        case 'about':
        case '--about':
        case '-a':
            Display = componentMap['About']
            commandTxt = ''
          break;

        case 'modern':
        case '--modern':
          view = 'modern'
          break;
      
        default:
          errorMsg = `${commandTxt} is not recoginized as a command`
          help = true
          commandTxt = ''
          break;
      }
    }
  }
</script>

<TailwindCss />

{#if view === 'modern'}
  <NormalView bind:view/>
{:else}
<div class='bg-slate-900 text-gray-400 m-3 font-ibm'>
  <Header />
  {#if help}
    <div class='text-sm my-2'>
      {#if errorMsg} 
      <p>{errorMsg}</p>
      {/if}
      <p>Commands:</p>
      <ul class='w-full md:w-1/2'>
        <li class='grid grid-cols-6'>about <span class='col-span-5'>display information about andrew riggs</span></li>
        <li class='grid grid-cols-6'>stack<span class='col-span-5'>display my tech stack</span></li>
        <li class='grid grid-cols-6'>links<span class='col-span-5'>list of social media links</span></li>
      </ul>
    </div>
  {/if}
  {#if Display}
    <Display />
  {/if}
  <div class='flex font-ibm text-sm my-2'>
    <span class='italic mr-2'>guest@andrewriggs$:</span>
    <input type="text" class='w-3/4 bg-slate-900 outline-none' bind:value={commandTxt} on:keypress={handleKeyPress} autofocus>
  </div>
</div>
{/if}

<style lang='postcss'>
  :root {
    @apply
      bg-slate-900;
  }
</style>