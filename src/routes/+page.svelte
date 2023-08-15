<script lang="ts">
  let startHandler = () => {
    let rolls = document.querySelectorAll("img.roll_icon");
    rolls.forEach((el) => {
      el.classList.add("running");
      el.classList.remove("fw");
      el.classList.remove("rew");
    });
  };
  let stopHandler = () => {
    let rolls = document.querySelectorAll("img.roll_icon");
    rolls.forEach((el) => {
      el.classList.remove("running");
      el.classList.remove("fw");
      el.classList.remove("rew");
    });
  };
  let rewHandler = () => {
    let rolls = document.querySelectorAll("img.roll_icon");
    rolls.forEach((el) => {
      el.classList.remove("running");
      el.classList.remove("fw");
      el.classList.add("rew");
    });
  };
  let fwHandler = () => {
    let rolls = document.querySelectorAll("img.roll_icon");
    rolls.forEach((el) => {
      el.classList.remove("running");
      el.classList.remove("rew");
      el.classList.add("fw");
    });
  };
</script>

<link
  href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"
  rel="stylesheet"
/>

<main>
  <div class="rew running fw" />
  <div class="flex_col">
    <div class="top_buttons">
      <button on:click={stopHandler}
        ><span class="material-symbols-outlined"> stop </span></button
      >
      <button on:click={startHandler}
        ><span class="material-symbols-outlined"> play_arrow </span></button
      >
      <button on:click={rewHandler}
        ><span class="material-symbols-outlined"> fast_rewind </span></button
      >
      <button on:click={fwHandler}
        ><span class="material-symbols-outlined"> fast_forward </span></button
      >
    </div>
    <div class="full_walkman">
      <div class="w_orange_top_btn" />
      <div class="walkman">
        <div class="w_body">
          <div class="line" />
          <img class="logo" alt="sony" src="logo.svg" width="150px" />
          <div class="cassette">
            <span class="c_name">Artist - Song</span>
            <div class="c_in">
              <div class="roll">
                <img class="roll_icon" src="roll.svg" alt="roll" />
              </div>
              <div class="whitebox" />
              <div class="roll">
                <img class="roll_icon" src="roll.svg" alt="roll" />
              </div>
            </div>
          </div>
          <img class="wlogo" alt="walkman" src="wlogo.svg" width="150px" />
        </div>
        <div class="w_side" />
      </div>
    </div>
  </div>
</main>

<style>
  .top_buttons {
    display: flex;
    flex-direction: row;
  }
  .logo {
    margin-top: 7rem;
    margin-left: 3rem;
  }
  .wlogo {
    margin-top: 1rem;
    margin-left: 3rem;
  }
  .walkman {
    display: flex;
    flex-direction: row;
  }
  .w_body {
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
    background-color: #30356c;
    width: 20rem;
    height: calc(100rem / 3);
  }
  .w_side {
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
    background-color: #ffffff;
    width: 5rem;
    height: calc(100rem / 3);
  }
  .w_orange_top_btn {
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
    background-color: #e8a125;
    width: 3rem;
    height: 1rem;
    margin-left: 4rem;
  }
  .line {
    border: 1px black solid;
    position: fixed;
    width: 19.7rem;
    margin-top: 5rem;
  }
  .cassette {
    display: flex;
    border: 10px;
    background-color: #000000;
    width: 8rem;
    margin-top: 1rem;
    margin-left: 3.75rem;
    height: calc(50rem / 3);
  }
  .roll {
    border-radius: 100%;
    width: 3rem;
    height: 3rem;
    border: 3px #826e41 solid;
    margin-left: 0.35rem;
  }
  .whitebox {
    border-radius: 0.5rem;
    margin-top: 10px;
    margin-bottom: 10px;
    height: 7rem;
    width: 4rem;
    background: #fff;
  }
  .roll_icon {
    color: #826e41;
    font-size: 65px;
  }
  .running {
    animation: rotation 1s infinite linear;
  }
  .rew {
    animation: rew 0.7s infinite linear;
  }
  .fw {
    animation: rotation 0.7s infinite linear;
  }
  @keyframes rew {
    from {
      transform: rotate(359deg);
    }
    to {
      transform: rotate(0deg);
    }
  }
  @keyframes rotation {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(359deg);
    }
  }
  .c_name {
    color: white;
    writing-mode: vertical-rl;
    text-orientation: mixed;
    transform: rotate(180deg);
    vertical-align: middle;
    text-align: center;
    height: 100%;
    margin-left: 20px;
    margin-right: 10px;
  }
  .c_in {
    margin-top: 15px;
  }
  .flex_col {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100dvh;
    width: 100dvw;
    flex-direction: column;
  }
</style>
