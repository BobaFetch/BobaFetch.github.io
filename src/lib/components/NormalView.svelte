<script>
  import Footer from "./Footer.svelte";
  import Projects from "./Projects.svelte";
  import { about } from '../data'

  const src = 'images/placeholder.jpeg'
  let colorMode = 'light'
  export let view
</script>

<div class={`${colorMode} flex flex-col md:grid md:grid-cols-12 gap-1 h-screen pb-3`}>
  <div class="md:col-span-6 mx-2 md:py-3 pt-3">
    <div class="flex flex-col gap-2">
      <div class={`${colorMode}-container border border-slate-900 flex flex-col items-center p-3 rounded-lg`}>
        <img src={src} class='rounded-full w-24 h-24' />
        <h2 class='text-5xl font-thin py-2'>ANDREW RIGGS</h2>
        <p>YOUR MOM SAID I'M A BAD INFLUENCE</p>
      </div>
      <div class={`${colorMode}-container rounded-lg p-3`}>
        <h2 class='text-center text-2xl font-thin'>TECHNOLOGIES</h2>
        <div class='flex justify-around font-light'>
          <ul>
            <li>
              JavaScript 
            </li>
            <li>
              nodeJs
            </li>
            <li>
              SQL
            </li>
            <li>MongoDB</li>
          </ul>
          <ul>
            <li>Go</li>
            <li>Python</li>
            <li>React</li>
            <li>Svelte</li>
          </ul>
        </div>
      </div>

      <div class={`${colorMode}-container border border-black p-3 rounded-lg`}>
        <h3 class='text-4xl font-thin text-center'>ABOUT</h3>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
        <!-- <p>{about}</p> -->
      </div>
    </div>
  </div>

  <div class='md:col-span-6 mx-2 py-3'>
    <Projects colorMode={colorMode} />
    
  </div>

  <div class={`${colorMode}-container md:col-span-12 mx-2 flex items-end h-fit rounded-lg`}>
    <Footer />
  </div>
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