<script>
  import { Icon } from '@steeze-ui/svelte-icon'
  import { Github, Linkedin, Twitter } from '@steeze-ui/feather-icons'
  import { spring } from 'svelte/motion'

  function bounce() {

  }
</script>

<div class='border border-black rounded-lg flex items-center justify-around w-full'>
  <!-- <svg xmlns="http://www.w3.org/2000/svg"> -->
    <!-- <circle cx="50" cy="50" r="30" fill='none' class='stroke-slate-900'> -->
      <a href='https://Github.com/bobafetch' class="border border-slate-900 w-fit h-fit rounded-full m-2 cursor-pointer hover:animate-pulse bg-gray-100">
        <Icon src={Github} size=50 class='stroke-slate-900 stroke-1 p-2'></Icon>
      </a>
    <!-- </circle> -->
  <!-- </svg> -->
      <a href='https://Twitter.com/bobafetch' class="border border-slate-900 w-fit h-fit rounded-full m-2 cursor-pointer hover:animate-pulse bg-gray-100">
        <Icon src={Twitter} size=50 class='stroke-slate-900 stroke-1 p-2'></Icon>
      </a>
      <a href='https://www.linkedin.com/in/andrew-riggs-09340763/' class="border border-slate-900 w-fit h-fit rounded-full m-2 cursor-pointer hover:animate-pulse bg-gray-100">
        <Icon src={Linkedin} size=50 class='stroke-slate-900 stroke-1 p-2'></Icon>
      </a>
  
</div>

<style>
  .test:hover {
    animation: spin 3s ease-in-out infinite;
  }

  @keyframes spin {
    0% { transform: rotateY(0deg);}
    /* 25% { transform: rotateY(190deg);} */
    50% { transform: rotateY(180deg);}
    /* 75% {transform: rotateY(240deg);} */
  }
</style>