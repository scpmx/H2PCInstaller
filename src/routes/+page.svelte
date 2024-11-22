<script lang="ts">
  import { invoke } from "@tauri-apps/api/core";

  let name = $state("");
  let greetMsg = $state("");

  async function greet(event: Event) {
    event.preventDefault();
    // Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
    greetMsg = await invoke("greet", { name });
  }
</script>

<div class="setup-container">
  <h1>Install Halo 2 Project Cartographer</h1>

  <label for="directory">Choose Directory:</label>
  <input type="text" id="directory" value="C:/Games/Halo 2 Project Cartographer">
  <button id="browse-button">Browse...</button>

  <button id="download-install-button">Download and Install</button>
  <button id="cancel-button">Cancel</button>

  <progress id="progress-bar" value="0" max="100"></progress>
  <p id="status-text">Ready to download...</p>
</div>

<style>
  .splash-container, .setup-container {
      text-align: center;
  }

  #setup-button, #download-install-button, #cancel-button {
      padding: 10px 20px;
      margin-top: 20px;
      background-color: #444;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 18px;
  }

  #setup-button:hover, #download-install-button:hover, #cancel-button:hover {
      background-color: #555;
  }

  #progress-bar {
      width: 100%;
      margin-top: 20px;
  }
</style>