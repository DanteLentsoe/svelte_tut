<script>
  import MobileNavBar from './Components/UI/NavigationBar/MobileNavBar.svelte'
  import { fade } from 'svelte/transition'
  let isNavOpen = false

  const toggleNavHandler = () => {
    isNavOpen = !isNavOpen
  }
</script>

<div class="min-h-full">
  <nav class="bg-gray-800">
    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
      <div class="flex h-16 items-center justify-between">
        <div class="flex items-center">
          <div class="flex-shrink-0">
            <img
              class="h-8 w-8"
              src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=500"
              alt="Your Company" />
          </div>
          <div class="hidden md:block">
            <div class="ml-10 flex items-baseline space-x-4">
              <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
              <a
                href="#"
                class="bg-gray-900 text-white px-3 py-2 rounded-md text-sm
                font-medium"
                aria-current="page">
                Dashboard
              </a>

              <a
                href="#"
                class="text-gray-300 hover:bg-gray-700 hover:text-white px-3
                py-2 rounded-md text-sm font-medium">
                Team
              </a>

              <a
                href="#"
                class="text-gray-300 hover:bg-gray-700 hover:text-white px-3
                py-2 rounded-md text-sm font-medium">
                Projects
              </a>

              <a
                href="#"
                class="text-gray-300 hover:bg-gray-700 hover:text-white px-3
                py-2 rounded-md text-sm font-medium">
                Calendar
              </a>

              <a
                href="#"
                class="text-gray-300 hover:bg-gray-700 hover:text-white px-3
                py-2 rounded-md text-sm font-medium">
                Reports
              </a>
            </div>
          </div>
        </div>
        <div class="hidden md:block">
          <div class="ml-4 flex items-center md:ml-6">
            <button
              type="button"
              class="rounded-full bg-gray-800 p-1 text-gray-400 hover:text-white
              focus:outline-none focus:ring-2 focus:ring-white
              focus:ring-offset-2 focus:ring-offset-gray-800">
              <span class="sr-only">View notifications</span>
              <!-- Heroicon name: outline/bell -->
              <svg
                class="h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                aria-hidden="true">
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M14.857 17.082a23.848 23.848 0 005.454-1.31A8.967 8.967 0
                  0118 9.75v-.7V9A6 6 0 006 9v.75a8.967 8.967 0 01-2.312
                  6.022c1.733.64 3.56 1.085 5.455 1.31m5.714 0a24.255 24.255 0
                  01-5.714 0m5.714 0a3 3 0 11-5.714 0" />
              </svg>
            </button>

            <!-- Profile dropdown -->
          </div>
        </div>
        <div class="-mr-2 flex md:hidden">
          <!-- Mobile menu button -->
          <button
            type="button"
            on:click={() => {
              console.log('clicked')
              toggleNavHandler()
            }}
            class="inline-flex items-center justify-center rounded-md
            bg-gray-800 p-2 text-gray-400 hover:bg-gray-700 hover:text-white
            focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2
            focus:ring-offset-gray-800"
            aria-controls="mobile-menu"
            aria-expanded="false">
            <span class="sr-only">Open main menu</span>
            <svg
              class="block h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              aria-hidden="true">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
            </svg>

            <svg
              class="hidden h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              aria-hidden="true">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile menu, show/hide based on menu state. -->

    {#if isNavOpen}
      <div in:fade>
        <MobileNavBar />
      </div>
    {/if}
  </nav>

</div>
