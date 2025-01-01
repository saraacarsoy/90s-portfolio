<script lang="ts">
  export let isOpen = false;
  export let closePopup;
  export let name = "";
</script>

{#if isOpen}
<div class="popup-overlay" on:click={closePopup}>
    <div class="popup" on:click|stopPropagation>
      <div class="popup-header">
        <span>{name}</span>
        <div class="close-button" on:click={closePopup}>
          <span>X</span>
        </div>
      </div>
      
      <div class="popup-content">
        <span>
          <u>S</u>ave
        </span>
        <div class="content-info">
          
        </div>
      </div>
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
    background-color: #ddd4da;
    padding: 5px;
    border-radius: 1px;
    box-shadow: 0 1px 2px #000;
    z-index: 100;
    user-select: none;
    min-width: 500px;
    border: 1px solid #252525;
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .popup-header {
    height: 25px;
    border: 1px solid #252525;
    display: flex;
    padding: 5px;
    align-items: center;
    justify-content: space-between;
  }

  .popup-content {
    padding: 0 7px;
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .content-info {
    border: 0.5px solid #252525;
    background-color: aquamarine;
    min-height: 200px;
  }

  .close-button {
    height: 100%;
    aspect-ratio: 1;
    border: 0.5px solid #252525;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>