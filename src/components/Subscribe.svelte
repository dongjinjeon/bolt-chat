<script>
  let email = '';

  function handleSubscribe() {
    // 여기에 구독 로직을 구현해야 합니다.
    alert(`${email}로 구독 신청되었습니다.`);
    email = '';
  }
</script>

<section class="subscribe">
  <h2>최신 포스트 구독하기</h2>
  <form on:submit|preventDefault={handleSubscribe}>
    <input type="email" bind:value={email} placeholder="이메일 주소를 입력하세요" required>
    <button type="submit">구독하기</button>
  </form>
</section>

<style>
  .subscribe {
    background-color: #f9f9f9;
    padding: 2rem;
    margin-top: 2rem;
    text-align: center;
  }

  form {
    display: flex;
    justify-content: center;
    margin-top: 1rem;
  }

  input {
    padding: 0.5rem;
    width: 300px;
    margin-right: 0.5rem;
  }

  button {
    padding: 0.5rem 1rem;
    background-color: #0066cc;
    color: white;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }
</style>