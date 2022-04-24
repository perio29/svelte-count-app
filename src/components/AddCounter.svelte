<script>
  import Modal from "./Modal.svelte";

  let modalOpen = false;

  const handleOpen = () => {
    modalOpen = !modalOpen;
  };
</script>

<div class="flex justify-end">
  <button
    on:click={handleOpen}
    class="block px-4 py-2 text-blue-900 border-2 border-blue-900 hover:bg-blue-900 hover:text-white border-solid rounded-lg"
    >新しいカウンターを作成</button
  >
  {#if modalOpen}
    <Modal on:open={handleOpen} />
  {/if}
</div>
