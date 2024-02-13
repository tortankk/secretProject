<script>

    import "@fontsource/pacifico";
    import letter from '../lib/media/letter.png';
    import 'add-to-calendar-button';

    import { Modals, closeModal, openModal, modals } from 'svelte-modals'
	import Modal from './Modal.svelte'

    import Modal2 from "./Modal2.svelte";

    let random_top = 65;
    let random_left = 40;
    function shuffle () {
        random_top = Math.floor(Math.random() * 65);
        random_left = Math.floor(Math.random() * 65);
        console.log(random_top, random_left);
    }

    function handleOpen() {
		openModal(Modal, { 
			title: `Marie`, 
			message: "This is an alert",
			onOpenAnother: () => {
				handleOpen()
			}
		})
	}

    
    function handleOpen2() {
		openModal(Modal2, { 
			title: `Marie`, 
			message: "This is an alert",
			onOpenAnother: () => {
				handleOpen2()
			}
		})
	}
</script>

<main>
  <div class ="whole-screen">
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <Modals>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div
        slot="backdrop"
        class="backdrop"
        on:click={closeModal}
      />
    </Modals>
    <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <img src={letter} alt="letter" class="letter" on:click={handleOpen}>

    
    <svg xmlns:xlink="http://www.w3.org/1999/xlink"
     id="canvas">
  <defs>
    <g id="heart">
      <g>
        <g>
          <path class="o_heart" d="M102.7,12.4L102.7,12.4C90.5,0.2,71.3-1,57.7,8.8c-13.6-9.9-32.9-8.7-45.2,3.5l0,0
                                   c-13.6,13.6-13.6,35.8,0,49.3L48.8,98c1.8,1.8,4,2.9,6.3,3.3c3.9,0.9,8.2-0.1,11.2-3.2l36.3-36.3C116.2,48.2,116.2,26,102.7,12.4
                                   z"/>
        </g>
      </g>
      <g>
        <g>
          <path class="i_heart" d="M74.7,34L74.7,34c-4.6-4.6-11.9-5.1-17.1-1.4c-5.2-3.8-12.5-3.3-17.1,1.3c-5.1,5.1-5.1,13.6,0,18.7
                                   l13.8,13.8c0.7,0.7,1.5,1.1,2.4,1.3c1.5,0.3,3.1-0.1,4.2-1.2l13.8-13.8C79.9,47.6,79.9,39.2,74.7,34z"/>
        </g>
      </g>
    </g>
  </defs>
</svg>

<span class="text">Be My Valentine?</span>
    <button type="button" class="position" on:mouseover={() => {shuffle()}} on:focus={() => {}} style="top: {random_top}%; left: {random_left}%;"
        >
        <span class="css-button-text">
            <span>No </span>
        </span>
    </button>
    <button  type="button"  class ="position  yes"on:click={handleOpen2}>
        <span class="css-button-text">
            <span>Yes</span>
        </span>
    </button>
  </div>
</main>

<style>
    :global(body) {
        padding: 0;
        margin: 0;
    }

    .yes {
        position: absolute !important;
        top: 65%;
        left: 60%;
    }

    .position:hover {
        cursor: pointer;
        color:white;
        background: #FFB3C3;
    }

    .backdrop {
        z-index: 999;
        position: fixed;
        top: 0;
        bottom: 0;
        right: 0;
        left: 0;
        background: rgba(0,0,0,0.50)
    }

    .letter {
        position: absolute;
        top: 5%;
        left: 90%;
        width : 50px;
    }

    .letter:hover {
        cursor: pointer;
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

    .position {
        position: absolute;
        transform: translate(-50%, -50%);
    }

    main {
        display: flex;
        padding: 0;
        margin: 0;
    }
    .whole-screen {
        padding: 0;
        margin: 0;
        width: 100%;
        height: 100vh;
        background:  url('../lib/media/sloth.png'), linear-gradient(#ffc0cb, #f48598);
        background-size: 60px;
    }

    .o_heart{
    fill: #FFB3C3;  
    }
    .i_heart{
        fill: #FCE3E9;
    }

.text{
  position: absolute;
  font-size: 3.5em;
  letter-spacing: 2px;
  font-family: 'pacifico';
  font-weight: normal;
  left: 50%;
  top: 45%;
  transform: translate(-50%, -50%);
  color: #FFB3C3;
  background: white;
  padding: 10px 20px;
  border-radius: 5px;
  border: 3px solid #FCE3E9;
  box-shadow: 0 5px 6px rgba(0, 0, 0, 0.1);
  white-space: nowrap;
}
.css-button-text {
	position: relative;
	padding: 10px 18px;
}
</style>