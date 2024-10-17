<script>
  export let navigate;
</script>

<header>
  <nav>
    <ul>
      <li><a href="/" on:click|preventDefault={() => navigate('home')}>홈</a></li>
      <li><a href="/blog" on:click|preventDefault={() => navigate('blog')}>블로그</a></li>
      <li><a href="/chat" on:click|preventDefault={() => navigate('chat')}>AI 챗봇</a></li>
    </ul>
  </nav>
</header>

<style>
  header {
    background-color: #f4f4f4;
    padding: 1rem;
  }

  nav ul {
    list-style-type: none;
    padding: 0;
    display: flex;
    justify-content: space-around;
  }

  nav a {
    text-decoration: none;
    color: #333;
    font-weight: bold;
  }
</style>