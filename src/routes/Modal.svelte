<script>
    import { closeModal, closeAllModals, openModal, modals } from 'svelte-modals'
      
    export let isOpen
    export let title
    export let message
    export let onOpenAnother
      
      let stackIndex = modals.length
  </script>
  
  {#if isOpen}
    <div role="dialog" class="modal">
      <div class="contents">
        <p>Marie</p>
        <p>I'm not very good at making statements, so I'm just going to say the things I like about you,</p>
        <p>I love your deeply selfless side, you care about me and the world around you, which is rare. </p>
        <p>I love your curiosity and your willingness to explore and try new things.</p>
        <p>I love the way you look after me when I'm ill.</p>
        <p>I love your midnight snacks.</p>
        <p>I love your papouilles and kisses.</p>
        <p>I love the happiness I get from your smile.</p>
        <p>I love your body and your eyes, your smile and your hair.</p>
        <p>I love the way my life is a little better every day I get to know you a little better.</p>
        <div class="actions">
                  {#if stackIndex > 1}
                      <button on:click={closeModal}>Close One</button>
                      <button on:click={closeAllModals}>Close All</button>				
                  {:else}
                      <button on:click={closeModal}>Close</button>
                  {/if}								
        </div>
      </div>
    </div>
  {/if}
  
  <style>
    p {
        margin-top : 0px !important;
        margin : 0px !important;
        display: flex !important;
    justify-content: flex-start !important;
    text-align: start !important;
    }
    .modal {
    z-index: 1000;
      position: fixed;
      top: 0;
      bottom: 0;
      right: 0;
      left: 0;
      display: flex;
      justify-content: center;
      align-items: center;
  
      /* allow click-through to backdrop */
      pointer-events: none;
    }

    button {
        letter-spacing: -1px;
        font-family: 'Dosis';
        font-weight: bold;
        z-index: 100;
        color: #FFB3C3;
        font-size: 19px;
        border-radius: 17px;
        border: solid 6px #f2bed1;
        text-decoration: none;
        cursor: pointer;
        overflow: hidden;
        font-family: Arial;
        font-weight: bold;
        background: white;
        display: inline-flex;
        align-items: center;
        padding: 0;
        border: 3px solid #FCE3E9;
        box-shadow: 0 5px 6px rgba(0, 0, 0, 0.1);
        letter-spacing: 2px;
        font-family: 'pacifico';
    }

    button:hover {
        cursor: pointer;
        color:white;
        background: #FFB3C3;
    }
  
    .contents {
        min-width: 240px;
    border-radius: 6px;
    padding: 16px;
    background: white;
    display: flex;
    flex-direction: column;
    pointer-events: auto;
    letter-spacing: -1px;
    font-family: 'Dosis';
    font-weight: bold;
    z-index: 100;
    color: #FFB3C3;
    font-size: 18px;
    border-radius: 17px;
    border: solid 6px #f2bed1;
    text-decoration: none;
    cursor: pointer;
    overflow: hidden;
    font-family: Arial;
    font-weight: normal;
    background: white;
    align-items: flex-start;
    padding: 0;
    border: 3px solid #FCE3E9;
    box-shadow: 0 5px 6px rgba(0, 0, 0, 0.1);
    letter-spacing: 2px;
    font-family: 'pacifico';
    align-content: flex-start;
    justify-content: center;
    padding: 30px;
    width: 450px;
    }
  
    h2 {
      text-align: center;
      font-size: 24px;
    }
  
    p {
      text-align: center;
      margin-top: 16px;
    }
  
    .actions {
      margin-top: 32px;
      display: flex;
      justify-content: space-between;
          gap: 8px;
    }
  
  </style>