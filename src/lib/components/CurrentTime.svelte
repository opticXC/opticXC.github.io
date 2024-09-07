<script lang="ts">
  let time = new Date();

  setInterval(() => {
    time = new Date();
  }, 1000);
</script>

<div class="Time">
  <h1>{time.toLocaleTimeString()}</h1>
</div>

<style lang="scss">
  .Time {
    border-radius: 4px;
    border: solid 1px #ffbb00;
    padding: 1rem;

    height: 10rem;
    width: 20rem;

    display: flex;
    justify-content: center;
    align-items: center;

    transition: cubic-bezier(0.165, 0.84, 0.44, 1) 0.3s;
  }
  .Time:hover {
    background-color: #ffbb00;
    color: #000;
    transform: scale(1.1);
  }
</style>
