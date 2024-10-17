<script>
  let messages = [];
  let newMessage = '';

  function sendMessage() {
    if (newMessage.trim() !== '') {
      messages = [...messages, { text: newMessage, sender: 'user' }];
      // 여기에 AI 응답 로직을 추가해야 합니다.
      // 지금은 간단한 에코 응답만 구현합니다.
      setTimeout(() => {
        messages = [...messages, { text: `에코: ${newMessage}`, sender: 'ai' }];
      }, 1000);
      newMessage = '';
    }
  }
</script>

<section class="chat-container">
  <h1>AI 챗봇</h1>
  
  <div class="chat-messages">
    {#each messages as message}
      <div class="message {message.sender}">
        <p>{message.text}</p>
      </div>
    {/each}
  </div>

  <div class="chat-input">
    <input type="text" bind:value={newMessage} placeholder="메시지를 입력하세요" on:keypress={(e) => e.key === 'Enter' && sendMessage()}>
    <button on:click={sendMessage}>전송</button>
  </div>
</section>

<style>
  .chat-container {
    max-width: 600px;
    margin: 0 auto;
    padding: 1rem;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  .chat-messages {
    height: 400px;
    overflow-y: auto;
    border: 1px solid #eee;
    padding: 1rem;
    margin-bottom: 1rem;
  }

  .message {
    margin-bottom: 1rem;
    padding: 0.5rem;
    border-radius: 5px;
  }

  .user {
    background-color: #e6f3ff;
    text-align: right;
  }

  .ai {
    background-color: #f0f0f0;
  }

  .chat-input {
    display: flex;
  }

  input {
    flex-grow: 1;
    padding: 0.5rem;
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