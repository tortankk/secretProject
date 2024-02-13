<script>
    import { closeModal, closeAllModals, openModal, modals } from 'svelte-modals'
    import 'add-to-calendar-button';

    import truc from '../lib/media/truc.png';

    export let isOpen
    export let title
    export let message
    export let onOpenAnother
      
      let stackIndex = modals.length
  </script>
  
  {#if isOpen}
    <div role="dialog" class="modal">
      <div class="contents">
        <p>Madame</p>
        <p>Marie LAAKMANN</p>
        <p>_</p>
        <p>I am delighted to announce that you have been selected and invited to a romance evening on Friday 23 February.</p>
        <br>
        <add-to-calendar-button
        name="Title"
        options="'Apple','Google', 'Outlook.com'"
        location="Dans ton coeur"
        startDate="2024-02-23"
        endDate="2024-02-23"
        startTime="19:00"
        endTime="23:59"
        timeZone="America/Los_Angeles"
        ></add-to-calendar-button>
        <img src={truc} alt="letter" class="ticket">
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
    add-to-calendar-button {
        font-size:200px !important;
    }
    .ticket {
        width: 180px;
        height: auto;
        align-self: center;
    }
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

    button:hover {
        cursor: pointer;
        color:white;
        background: #FFB3C3;
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