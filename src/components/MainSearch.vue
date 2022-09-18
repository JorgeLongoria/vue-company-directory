<template>
  <div class="wrapper">
    <input type="text" placeholder="Search Staff Member" class="search" />
    <span class="icon">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-6 w-6">
        <path d="M8.25 10.875a2.625 2.625 0 115.25 0 2.625 2.625 0 01-5.25 0z" />
        <path
          fill-rule="evenodd"
          d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25zm-1.125 4.5a4.125 4.125 0 102.338 7.524l2.007 2.006a.75.75 0 101.06-1.06l-2.006-2.007a4.125 4.125 0 00-3.399-6.463z"
          clip-rule="evenodd"
        />
      </svg>
    </span>
  </div>
</template>

<style scoped lang="postcss">
  .wrapper {
    @apply relative flex w-full items-stretch;
    .search {
      @apply rounded-md border-0 px-3 py-4 text-gray-800 placeholder-gray-400 outline-none focus:ring focus:ring-black;
    }
    .icon {
      @apply absolute right-0 py-4 pr-8 text-gray-800;
    }
  }
</style>