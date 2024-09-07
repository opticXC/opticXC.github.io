<script lang="ts">
</script>

<div class="bookmarks">
  <div class="icon"></div>
</div>

<style lang="scss">
  .bookmarks {
    border-radius: 4px;
    border: solid 1px #ffbb00;
    padding: 1rem;

    height: 10rem;
    width: 20rem;

    display: flex;
    justify-content: start;
    align-items: center;

    transition: cubic-bezier(0.165, 0.84, 0.44, 1) 0.3s;
  }
  .icon {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 1rem;
    width: 5rem;
  }
  .icon:hover {
    transform: scale(1.1);
  }
</style>
