<script>
  import "../app.css";
  import Header from '../components/shared/header.svelte';
</script>


<div class="min-h-screen bg-gradient-to-r from-cyan-500 to-blue-500">
  <Header />
  <div class="max-w-xs py-12 mx-auto sm:max-w-screen-sm md:max-screen-md lg:max-w-screen-lg xl:max-w-screen-xl">
    <div class="w-full bg-white shadow-lg rounded">
      <slot />
    </div>
 </div>
</div>
