<script>
  import { onMount } from "svelte";

  const username = "opticXC";
  const url = `https://api.github.com/users/${username}`;

  let data = {};

  onMount(async () => {
    const response = await fetch(url);
    data = await response.json();
  });
</script>

<div class="github">
  <div class="image-container">
    <img class="avatar" src={data.avatar_url} alt="avatar" width="128" />
  </div>
  <div class="git-info-container">
    <a target="_blank" href={data.html_url}>
      {username.toLocaleLowerCase()}
    </a>
    <p>{data.bio}</p>
  </div>
</div>

<style lang="scss">
  .github {
    width: 15rem;
    height: 20rem;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    border-radius: 4px;
    border: solid 1px #ffbb00;
    padding: 1rem;

    transition: cubic-bezier(0.165, 0.84, 0.44, 1) 0.3s;
  }
  .github:hover {
    transform: scale(1.1);
    background-color: #ffbb00;
    color: #000;
  }
  .github:hover a {
    color: #000;
  }

  .github a {
    color: #ffbb00;
    padding: 1px;
  }

  .git-info-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    width: 20rem;
  }

  .image-container {
    display: flex;
    justify-content: center;
  }

  .avatar {
    border-radius: 4px;
  }
</style>
