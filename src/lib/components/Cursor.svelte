<script lang="ts">
  import { onMount } from "svelte";
  import { linear } from "svelte/easing";

  let cursor: HTMLElement | null;
  let tail: HTMLElement | null;

  onMount(() => {
    cursor = document.getElementById("cursor");
    tail = document.getElementById("tail");
  });
  2;
  window.addEventListener("mousemove", (e) => {
    if (cursor) {
      cursor.style.left = e.clientX + "px";
      cursor.style.top = e.clientY + "px";
    }

    if (tail) {
      tail.style.left = e.clientX + "px";
      tail.style.top = e.clientY + "px";
    }
  });

  setInterval(() => {}, 1000);
</script>

<div>
  <div id="cursor" class="cursor">
    <svg>
      <circle cx="10" cy="10" r="4" fill="white" />
    </svg>
  </div>

  <div id="tail" class="cursor-tail">
    <svg>
      <circle cx="10" cy="10" r="8" fill="white" />
    </svg>
  </div>
</div>

<style lang="scss">
  .cursor {
    position: fixed;
    pointer-events: none;
    z-index: 9999;
    width: 20px;
    height: 20px;
    transform: translate(-50%, -50%);
  }

  .cursor-tail {
    position: fixed;
    pointer-events: none;
    z-index: 9998;
    width: 20px;
    height: 20px;
    transform: translate(-50%, -50%);
    transition: cubic-bezier(0.165, 0.84, 0.44, 1) 0.3s;
  }

  svg {
    width: 20px;
    height: 20px;
  }

  circle {
    transition: cubic-bezier(0.165, 0.84, 0.44, 1) 0.3s;
  }
</style>
