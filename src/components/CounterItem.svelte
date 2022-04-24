<script>
  import { counters } from "../store";
  import { fade, scale } from "svelte/transition";

  const increment = (i) => {
    $counters[i].count += 1;
  };

  const decrement = (i) => {
    $counters[i].count -= 1;
  };

  const reset = (i) => {
    $counters[i].count = 0;
  };

  const handleDelete = (i) => {
    $counters.splice(i, 1);
    $counters = $counters;
  };
</script>

<div>
  {#each $counters as item, index}
    <div
      class="px-3 py-3 w-3/5 mx-auto mt-3 text-center flex items-center justify-between bg-gray-200"
      in:scale
      out:fade={{ duration: 500 }}
    >
      <input
        type="text"
        bind:value={item.title}
        class="text-black px-3 py-2 border-none rounded-md"
      />
      <p class="text-3xl">{item.count}</p>
      <div class="flex">
        <button
          class="px-3 py-2 bg-red-500 text-white block rounded-l-sm"
          on:click={() => increment(index)}
        >
          +
        </button>

        <button
          class="px-3 py-2 bg-blue-500 text-white block"
          on:click={() => decrement(index)}
        >
          -
        </button>
        <button
          class="px-3 py-2 bg-yellow-400 text-white block rounded-r-sm"
          on:click={() => reset(index)}
        >
          0
        </button>
      </div>
      <div>
        <button
          on:click={() => handleDelete(index)}
          class="bg-blue-900 hover:bg-blue-600 text-white px-3 py-2 rounded-md border-0"
          >削除</button
        >
      </div>
    </div>
  {/each}
</div>

<div class="mt-6 flex justify-center text-2xl">
  <p>カウンターの合計：</p>
  <p>
    {$counters.reduce(function (sum, element) {
      return sum + element.count;
    }, 0)}
  </p>
</div>
