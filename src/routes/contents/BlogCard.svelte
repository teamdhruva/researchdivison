<script>
  import { marked } from 'marked'; // Import the marked library to parse markdown

  export let post; // The post data passed from the parent component
  
  let isModalOpen = false; // State to handle modal visibility
  let htmlContent = ''; // Variable to store the parsed HTML content

  // Function to toggle modal open/close
  function toggleModal() {
    isModalOpen = !isModalOpen;
  }

  // Convert markdown content to HTML using marked
  $: htmlContent = marked(post.markdownContent); // Automatically parse markdown when post changes
</script>

<style>
  /* Card styles */
  .card {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    max-width: 300px;
    margin: 20px auto;
    transition: transform 0.3s ease;
  }

  .card:hover {
    transform: scale(1.05);
  }

  .card-header {
    font-size: 1.25rem;
    font-weight: bold;
    margin-bottom: 10px;
  }

  .card-content {
    font-size: 1rem;
    color: #555;
  }

  /* Modal styles */
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10;
  }

  .modal-content {
    background:white;
    padding: 30px;
    border-radius: 8px;
    max-width: 800px;
    max-height: 80%;
    overflow-y: auto;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  }

  .close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    background: #f44336;
    color: #fff;
    border: none;
    border-radius: 50%;
    width: 30px;
    height: 30px;
    cursor: pointer;
    font-size: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .close-btn:hover {
    background: #d32f2f;
  }
</style>

<!-- Blog card displayed on the main page -->
<div class="card" on:click={toggleModal}>
  <div class="card-header">{post.title}</div>
  <div class="card-content">
    <p>Click here to read the full post in Markdown.</p>
  </div>
</div>

<!-- Modal that opens when a card is clicked -->
{#if isModalOpen}
  <div class="modal" on:click={toggleModal}>
    <div class="modal-content" on:click|stopPropagation>
      <button class="close-btn" on:click={toggleModal}>X</button>
      <article class="markdown-content">
        <!-- Render parsed HTML using @html directive -->
        {#if htmlContent}
          {@html htmlContent}
        {/if}
      </article>
    </div>
  </div>
{/if}
