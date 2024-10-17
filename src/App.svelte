<script>
  import { onMount } from 'svelte';
  import Header from './components/Header.svelte';
  import Footer from './components/Footer.svelte';
  import Home from './pages/Home.svelte';
  import Blog from './pages/Blog.svelte';
  import AIChat from './pages/AIChat.svelte';
  import Subscribe from './components/Subscribe.svelte';

  let currentPage = 'home';

  function navigate(page) {
    currentPage = page;
  }

  onMount(() => {
    // 여기에 필요한 초기화 로직을 추가할 수 있습니다.
  });
</script>

<main>
  <Header {navigate} />
  
  {#if currentPage === 'home'}
    <Home />
  {:else if currentPage === 'blog'}
    <Blog />
  {:else if currentPage === 'chat'}
    <AIChat />
  {/if}

  <Subscribe />
  <Footer />
</main>

<style>
  :global(body) {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
  }
</style>