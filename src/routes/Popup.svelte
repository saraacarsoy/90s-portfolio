<script>
    export let isOpen = false;
    export let closePopup;
</script>

{#if isOpen}
<div class="popup-overlay" on:click={closePopup}>
    <div class="popup" on:click|stopPropagation>
    <p>File opened!</p>
    <button on:click={closePopup}>Close</button>
    </div>
</div>
{/if}

<style>
    .popup-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  
    .popup {
      background-color: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      z-index: 100;
    }
</style>