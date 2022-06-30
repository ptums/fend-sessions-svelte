<script>
 let isMobileOpen = false;
  import FaBars from 'svelte-icons/fa/FaBars.svelte'
  import FaTimes from 'svelte-icons/fa/FaTimes.svelte'
  const openMenu = () => { isMobileOpen = !isMobileOpen;};
  const closeMenu = () => { isMobileOpen = false }

 const menuItems = [
  {
    url: "/",
    label: "Sessions"
  }, 
  {
     url: "/tutorials",
     label: "Tutorials"

  },
  {
     url: "/games",
     label: "Games"

  },
  {
     url: "/contact",
     label: "Contact"

  }
 ]
</script>

<nav class="hidden sm:block sm:w-full bg-white shadow px-2 sm:px-6 lg:px-8">
  <div class="relative flex justify-between h-16">
  <div class="flex items-center justify-center flex-1 sm:items-stretch sm:justify-start">
    <div class="flex items-center flex-shrink-0">
      <h1 class="text-3xl font-bold">FEND Session</h1>
   </div>
   <div class="sm:ml-6 sm:flex sm:items-center">
    <ul class="hidden sm:ml-6 sm:flex sm:space-x-8">
      {#each menuItems as item}
        <li>
         <a 
            class="inline-flex items-center h-16 px-1 pt-1 text-sm font-medium text-gray-500 border-b-2 border-transparent cursor-pointer hover:border-gray-300 hover:text-gray-700"
            href={item.url}>
            {item.label}
		      </a>
        </li>
      {/each}
    </ul>

  </div>
  </div>
</nav>

<button
  class="block w-12 h-12 relative rounded left-2 top-2 bg-white p-2 sm:hidden" 
  on:click={openMenu}
>
  {#if isMobileOpen}
    <FaTimes />	
  {:else}
    <FaBars />
  {/if}
 </button>
 {#if isMobileOpen}
  <div class="bg-white absolute top-0 left-0 w-full min-h-screen">
    <div class="w-full flex justify-end">
      <button class="w-12 h-12 relative right-2 top-2" on:click={closeMenu}>
        <FaTimes />
      </button>
    </div>
     <ul class="ml-6 text-xl flex flex-col">
      {#each menuItems as item}
        <li class="mb-8">
         <a 
            class="hover:underline"
            href={item.url}>
            
            {item.label}
		      </a>
        </li>
      {/each}
    </ul>
  
  </div>
{/if}

