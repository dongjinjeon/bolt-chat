<script>
  let posts = [
    { id: 1, title: '최신 웹 개발 트렌드 2023', content: '...', date: '2023-05-01', category: '웹개발', tags: ['트렌드', 'JavaScript', 'React'] },
    { id: 2, title: 'AI와 웹 개발의 융합', content: '...', date: '2023-04-28', category: 'AI', tags: ['머신러닝', '웹개발', 'API'] },
    { id: 3, title: '프론트엔드 프레임워크 비교', content: '...', date: '2023-04-25', category: '프론트엔드', tags: ['React', 'Vue', 'Angular'] },
  ];

  let searchKeyword = '';
  let selectedCategory = '';
  let selectedTag = '';

  $: filteredPosts = posts.filter(post => 
    post.title.toLowerCase().includes(searchKeyword.toLowerCase()) &&
    (selectedCategory === '' || post.category === selectedCategory) &&
    (selectedTag === '' || post.tags.includes(selectedTag))
  );

  function handleSearch() {
    // 검색 로직은 이미 반응형으로 구현되어 있습니다.
  }
</script>

<section>
  <h1>블로그</h1>
  
  <div class="search-filter">
    <input type="text" bind:value={searchKeyword} placeholder="검색어를 입력하세요" on:input={handleSearch}>
    <select bind:value={selectedCategory}>
      <option value="">모든 카테고리</option>
      <option>웹개발</option>
      <option>AI</option>
      <option>프론트엔드</option>
    </select>
    <select bind:value={selectedTag}>
      <option value="">모든 태그</option>
      <option>JavaScript</option>
      <option>React</option>
      <option>머신러닝</option>
      <option>API</option>
      <option>Vue</option>
      <option>Angular</option>
    </select>
  </div>

  <div class="posts">
    {#each filteredPosts as post}
      <article>
        <h2>{post.title}</h2>
        <p>{post.content.substring(0, 150)}...</p>
        <div class="meta">
          <span>{post.date}</span>
          <span>{post.category}</span>
          {#each post.tags as tag}
            <span class="tag">{tag}</span>
          {/each}
        </div>
      </article>
    {/each}
  </div>
</section>

<style>
  .search-filter {
    margin-bottom: 2rem;
  }

  input, select {
    margin-right: 1rem;
    padding: 0.5rem;
  }

  .posts article {
    margin-bottom: 2rem;
    border-bottom: 1px solid #eee;
    padding-bottom: 1rem;
  }

  .meta {
    font-size: 0.9rem;
    color: #666;
  }

  .tag {
    background-color: #f0f0f0;
    padding: 0.2rem 0.5rem;
    border-radius: 3px;
    margin-right: 0.5rem;
  }
</style>