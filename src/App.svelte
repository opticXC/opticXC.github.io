<script lang="ts">
  import Bookmarks from "./lib/components/Bookmarks.svelte";
  import CurrentTime from "./lib/components/CurrentTime.svelte";
  import Cursor from "./lib/components/Cursor.svelte";
  import Github from "./lib/components/Github.svelte";

  import { onMount } from "svelte";

  let cursor = { x: 0, y: 0 };

  onMount(() => {
    window.addEventListener("mousemove", (e) => {
      cursor = { x: e.clientX, y: e.clientY };
    });
  });
</script>

<div class="box">
  <div class="dashboard">
    <Github />
    <div class="sidebar">
      <CurrentTime />
      <Bookmarks />
    </div>
  </div>
  <div class="cursor-container">
    <Cursor />
  </div>
</div>

<style lang="scss">
  .box {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .dashboard {
    border-radius: 4px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    margin: 20px;
    gap: 20px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }

  .sidebar {
    display: flex;
    flex-direction: column;
    align-items: start;
    height: 20rem;
    width: 20vw;
    gap: 1rem;
  }

  .cursor-container {
    position: fixed;
    pointer-events: none;
    z-index: 9999;
  }
</style>
