<script>
  let count = 0;

  const increment = () => {
    count += 1;
  }

  const decrement = () => {
    count -= 1;
  }

  const reset = () => {
    count = 0;
  }
</script>

<div>
  <div class="px-2 py-3 w-3/5 mx-auto mt-3 text-center flex items-center justify-between bg-gray-300">
    <input type="text" placeholder="new" class="text-gray-400" />
    <p class="text-3xl">{count}</p>
    <div class="flex">
      <button class="px-3 py-2 bg-red-500 text-white block rounded-l-sm" on:click={increment}>
        +
      </button>
      
      <button class="px-3 py-2 bg-blue-500 text-white block" on:click={decrement}>
        -
      </button>
      <button class="px-3 py-2 bg-yellow-400 text-white block rounded-r-sm" on:click={reset}>
        0
      </button>
    </div>
  </div>
</div>