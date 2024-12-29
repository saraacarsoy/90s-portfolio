<script lang="ts">
    import Popup from './Popup.svelte';
    import { onMount, onDestroy } from 'svelte';
  
    export let name = "";
  
    let selected = false;
    let isPopupOpen = false;
  
    let fileElement: HTMLDivElement;
  
    function handleSingleClick() {
      selected = !selected;
    }
  
    function handleDoubleClick() {
      isPopupOpen = true;
    }
  
    function closePopup() {
      isPopupOpen = false;
    }
  
    function handleClickOutside(event: MouseEvent) {
        if (fileElement && event.target instanceof Node && !fileElement.contains(event.target)) {
            selected = false;
        }
    }
  
    onMount(() => {
      document.addEventListener('click', handleClickOutside);
    });
  
    onDestroy(() => {
      document.removeEventListener('click', handleClickOutside);
    });
  </script>
  
  <div class="file-container">
    <div
      bind:this={fileElement}
      class="file"
      on:click={handleSingleClick}
      on:dblclick={handleDoubleClick}>
    </div>
    <span class="file-name {selected ? 'selected' : ''}">{name}</span>
  
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

    .file-name {
        color: black;
        padding: 2px;
        user-select: none;
    }

    .file-name.selected {
        background-color: #09016f;
        border: 1px dotted #8c8dcd;
        color: white;
        padding: 1px;
    }
</style>
