<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import { page } from '$app/stores';
	
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="min-h-screen flex flex-col">
  <header class="sticky top-0 z-50">
  <div class="bg-gradient-to-r from-blue-700 to-blue-600 text-white shadow-md">
    <div class="mx-auto flex items-center p-4">

      <!-- Company Name -->
      <div class="text-2xl font-bold tracking-wide mr-auto">
        <a href="/">Manufacturing Co.</a>
      </div>

      <!-- Centered Navigation -->
      <nav class="absolute left-1/2 transform -translate-x-1/2 flex gap-8 text-lg">
        <a
          href="/"
          class="transition-colors duration-200 hover:text-gray-200 
          { $page.url.pathname === '/' ? 'font-semibold border-b-2 border-white pb-1' : '' }"
        >
          Home
        </a>
        <a
          href="/services"
          class="transition-colors duration-200 hover:text-gray-200
          { $page.url.pathname === '/services' ? 'font-semibold border-b-2 border-white pb-1' : '' }"
        >
          Services
        </a>
        <a
          href="/about"
          class="transition-colors duration-200 hover:text-gray-200
          { $page.url.pathname === '/about' ? 'font-semibold border-b-2 border-white pb-1' : '' }"
        >
          About
        </a>
        <a
          href="/contact"
          class="transition-colors duration-200 hover:text-gray-200
          { $page.url.pathname === '/contact' ? 'font-semibold border-b-2 border-white pb-1' : '' }"
        >
          Contact
        </a>
      </nav>

    </div>
  </div>
</header>

  <div class="p-8 flex-1 p-6 max-w-4xl mx-auto w-full">
	{@render children()}
  </div>
  
<footer class="bg-gray-100 border-t border-gray-200">
  <div class="max-w-4xl mx-auto px-6 py-8 text-sm text-gray-600 flex flex-col md:flex-row items-center justify-between gap-4">

    <!-- Left: Copyright -->
    <div>
      © 2025 Small Manufacturing Co.
    </div>

    <!-- Right: Footer Navigation -->
    <nav class="flex gap-6">
      <a href="/about" class="hover:text-blue-700 transition">
        About
      </a>
      <a href="/services" class="hover:text-blue-700 transition">
        Services
      </a>
      <a href="/careers" class="hover:text-blue-700 transition">
        Careers
      </a>
      <a href="/contact" class="hover:text-blue-700 transition">
        Contact
      </a>
    </nav>

  </div>
</footer>

</div>
