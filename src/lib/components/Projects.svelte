<script>
  import { fly } from 'svelte/transition'
  import { projects } from '../data'
  import { Icon } from '@steeze-ui/svelte-icon'
  import { ChevronLeft, ChevronRight } from '@steeze-ui/feather-icons'
  import { onDestroy, onMount } from 'svelte';

  export let colorMode;
  let projectKey = 1

  let myInterval

  function handleProject(e) {
   if (e.target.parentElement.value === 'next' || e.target.value === 'next') {
    if (projectKey >= projects.length) {
      projectKey = 1
    } else {
      projectKey++
    }
   } else if (e.target.parentElement.value === 'prev' || e.target.value === 'prev') {
    if (projectKey <=1) {
      projectKey = projects.length
    } else {
      projectKey--
    }
   }
  }

  function scrollProjects() {
    myInterval = setInterval(() => {
      if (projectKey >= projects.length) {
        projectKey = 1
      } else {
        projectKey++
      }
    }, 8000)
  }

  function stopScroll() {
    clearInterval(myInterval)
  }

  onMount(() => {
   scrollProjects()
  })

  onDestroy(() => stopScroll())
</script>

<div class={`${colorMode}-container rounded-lg relative h-full p-3`}>
  {#each projects as project}
    {#if project.key === projectKey}
      <div in:fly={{x:200, duration: 300}} on:mouseenter={stopScroll} on:mouseleave={scrollProjects}>
        <h3 class='text-2xl font-light italic text-center'>{project.name}</h3>
        <p class=''>{project.description}</p>
        <h4 class='text-center text-xl font-light'>STACK</h4>
        <ul>
          {#each project.tech as tech}
            <li>{tech}</li>
          {/each}
        </ul>
      </div>
        <!-- only display buttons when needed -->
        <button 
          on:click|preventDefault={handleProject} value='prev'
          class='absolute left-0 top-0 h-full text-gray-400 hover:text-white opacity-25 hover:opacity-100 cursor-pointer'
        >
          <Icon src={ChevronLeft} size={'30'} class='stroke-1' />
        </button>
        <button 
          on:click={handleProject} value='next'
          class='absolute right-0 top-0  h-full text-gray-400 hover:text-white opacity-25 hover:opacity-100 cursor-pointer'>
          <Icon src={ChevronRight} size={'30'} class='stroke-1' />
        </button>
    {/if}
  {/each}
</div>

<style lang='postcss'>
  .dark {
    @apply 
      bg-slate-900
      text-gray-200;
  }

  .dark-container {
    @apply
      bg-blue-100 
      text-slate-900;
  }

  .light {
    @apply
      bg-gray-100
      text-slate-900;
  }

  .light-container {
    @apply
      bg-slate-700
      text-gray-200;
  }

  
</style>