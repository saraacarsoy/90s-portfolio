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
        <section class="content-info">
          <img src="/background.png" class="about-image" alt="">
        </section>
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
    max-width: 650px;
    max-height: 500px;
  }

  .content-info {
    position: relative;
    border: 0.5px solid #252525;
    overflow-y: auto;
    font-family: 'Courier New', Courier, monospace;
    color: #000;
    font-size: 16px;
  }

  .about-image {
    width: 100%;
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