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
          <span>About me</span>
          <div class="content-text">Hi there! I’m Sara, an artsy programmer with almost 5 years of experience diving into all things code. My daily playgrounds are Java, JavaScript/TypeScript (hello Aurelia fans! *insert cricket chirp*), and PL/SQL. But when it comes to HTML and CSS, I’m all in.</div>
          <div class="content-text">I graduated from Sabanci University in Istanbul with a degree in Computer Science and Engineering (50% scholarship, woo!) and later got my Master’s in Serious Games from the University of Skövde, also with a 50% scholarship. Currently, I’m working as a software consultant at Piktiv AB, where I’ve spent the last 3+ years helping a fintech company bring their ideas to life.</div>
          <div class="content-text">When I’m not coding, you’ll probably find me crocheting, sketching some 2D illustrations, or fiddling with 3D modeling. Oh, and I am currently obsessed with Baldur’s Gate.</div>
          <div class="side-text">So, welcome and hope you will like your stay!</div>

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
  }

  .content-info {
    position: relative;
    border: 0.5px solid #252525;
    overflow-y: auto;
    font-family: 'Courier New', Courier, monospace;
    color: #000;
    padding: 2rem;
    font-size: 16px;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .about-image {
    width: 100%;
    position: absolute;
    z-index: -1;
    left: 0;
    top: 0;
  }

  .content-text {
    max-width: 650px;
    margin-right: 37%;
  }

  .side-text {
    max-width: 150px;
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