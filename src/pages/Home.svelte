<script>
  let latestPosts = [
    { title: '최신 웹 개발 트렌드 2023', date: '2023-05-01' },
    { title: 'AI와 웹 개발의 융합', date: '2023-04-28' },
    { title: '프론트엔드 프레임워크 비교', date: '2023-04-25' },
  ];
</script>

<section>
  <h1>웹개발과 AI의 만남</h1>
  <p>최신 웹개발 트렌드와 AI 기술에 대한 인사이트를 제공합니다.</p>
  
  <h2>최신 포스트</h2>
  <ul>
    {#each latestPosts as post}
      <li>
        <a href="/blog">{post.title}</a>
        <span>{post.date}</span>
      </li>
    {/each}
  </ul>
</section>

<style>
  section {
    margin-top: 2rem;
  }

  h1 {
    font-size: 2.5rem;
    color: #333;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    margin-bottom: 1rem;
  }

  a {
    color: #0066cc;
    text-decoration: none;
  }

  span {
    color: #666;
    font-size: 0.9rem;
    margin-left: 1rem;
  }
</style>