<script>
  import Popup from './Popup.svelte'; 
  
  export let name = "";

  let selected = false;
  let isPopupOpen = false;

  function handleSingleClick() {
    selected = !selected;
  }

  function handleDoubleClick() {
    isPopupOpen = true;
  }

  function closePopup() {
    isPopupOpen = false;
  }
</script>

<div class="file-container">
    <div
        class="file {selected ? 'selected' : ''}"
        on:click={handleSingleClick}
        on:dblclick={handleDoubleClick}>
    </div>
    <span class="file-name">{name}</span>

    <Popup isOpen={isPopupOpen} closePopup={closePopup} />
</div>

<style>
    .file-container {
        display: flex;
        flex-direction: column;
        gap: 10px;
        align-items: center;
    }

	.file {
		background-color: #fef4a7;
		border: 1px solid #5d604b;
        height: 40px;
        width: 60px;
        position: relative;
        transition: background-color 0.3s, box-shadow 0.3s;
	}

    .file:before {
        content: '';
        width: 27px;
        height: 12px;
        border-radius: 4px 10px 0 0;
        background-color: #fef4a7;
        border: 1px solid #5d604b;
        position: absolute;
        top: -10px;
        z-index: -1;
        transition: background-color 0.3s, border-color 0.3s;
    }

    .file.selected {
        background-color: #3399ff;
        border-color: #0066cc;
        box-shadow: 0 0 0 5px rgba(51, 153, 255, 0.5);
    }

    .file.selected:before {
        background-color: #3399ff;
        border-color: #0066cc;
        box-shadow: 0 0 0 5px rgba(51, 153, 255, 0.5);
    }
</style>
