<script>
  import { counters } from "../store";
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let title = "";

  const handleAddCounter = () => {
    $counters = [...$counters, { title: title, count: 0 }];
    title = "";
  };

  const modalClose = () => {
    dispatch("open");
  };
</script>

<div
  class="w-full h-full fixed top-0 left-0 bg-gray-800 bg-opacity-50 z-50 flex justify-center items-center"
>
  <div
    class=" md:w-2/5 md:h-2/5 w-2/3 h-2/3 bg-white flex items-center justify-center"
  >
    <div>
      <input
        class="block px-3 py-2 border-2 border-blue-300 rounded-md w-40 md:w-64 mb-5"
        type="text"
        placeholder="タイトルを入力してください"
        bind:value={title}
      />
      <div on:click={modalClose}>
        <button
          disabled={title === ""}
          class="block px-3 py-2 border-none bg-blue-900 text-white rounded-md mx-auto mb-14"
          on:click={handleAddCounter}>カウンターを追加</button
        >
      </div>
      <div>
        <button
          class="block px-3 py-2 border-none bg-gray-400 text-black rounded-md mx-auto"
          on:click={modalClose}>閉じる</button
        >
      </div>
    </div>
  </div>
</div>
