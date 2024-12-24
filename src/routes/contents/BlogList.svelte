<script>
  export let blogs;
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  function selectBlog(blog) {
    dispatch('selectBlog', blog); // Emit blog selection event
  }
  function scrollBlogs(direction) {
    const container = document.querySelector('.blog-slider');
    const scrollAmount = container.clientWidth;
    container.scrollBy({
      left: direction * scrollAmount,
      behavior: 'smooth'
    });
  }
</script>

<div class="blog-container">
  <h2>Blogs</h2>
  <div class="blog-slider">
    <div class="blog-list">
      {#each blogs as blog}
        <div class="blog-card" on:click={() => selectBlog(blog)}>
          <img class="blog-image" src={blog.image} alt={blog.title} />
          <div class="blog-content">
            <h3>{blog.title}</h3>
            <p>{blog.description}</p>
            <small>Author: {blog.author}</small>
          </div>
        </div>
      {/each}
    </div>
  </div>
  <button class="nav prev" on:click={() => scrollBlogs(-1)}>&lt;</button>
  <button class="nav next" on:click={() => scrollBlogs(1)}>&gt;</button>
</div>

<style>
  .blog-container {
    position: relative;
    width: 100%;
    overflow: hidden;
  }

  h2 {
    text-align: center;
    margin-bottom: 20px;
    color: #fff; /* White text for the heading */
  }

  .blog-slider {
    display: flex;
    overflow-x: auto;
    scroll-behavior: smooth;
    scrollbar-width: none; /* For Firefox */
  }

  .blog-slider::-webkit-scrollbar {
    display: none; /* For Chrome, Safari, and Edge */
  }

  .blog-list {
    display: flex;
    gap: 20px;
    padding: 10px;
  }

  .blog-card {
    flex: 0 0 calc(33.33% - 20px); /* Three cards per row */
    max-width: calc(33.33% - 20px);
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.5);
    border-radius: 10px;
    overflow: hidden;
    background: #121212; /* Dark background for the card */
    border: 2px solid white; /* White border */
    cursor: pointer;
    transition: transform 0.3s, box-shadow 0.3s;
    text-align: left;
    display: flex;
    flex-direction: column;
    max-width: 250px;
  }

  .blog-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 6px 12px rgba(255, 255, 255, 0.2);
  }

  .blog-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-bottom: 1px solid #333; /* Subtle border for separation */
  }

  .blog-content {
    padding: 15px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;
    background: #1c1c1c; /* Slightly lighter shade for text area */
    color: #fff; /* White text for readability */
    height: 40%;
  }

  .blog-card h3 {
    font-size: 1.2rem;
    font-weight: 600;
    margin: 0;
    color: #ffcc00; /* Accent color for titles */
  }

  .blog-card p {
    font-size: 1rem;
    margin: 0;
    color: #ddd; /* Light gray for description */
    line-height: 1.6;
  }

  .blog-card small {
    font-size: 0.9rem;
    color: #999; /* Subtle gray for the author text */
  }

  .nav {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0, 0, 0, 0.7);
    color: white;
    border: none;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    cursor: pointer;
    z-index: 10;
  }

  .nav.prev {
    left: 10px;
  }

  .nav.next {
    right: 10px;
  }

  /* Responsive Design */
  @media (max-width: 768px) {
    .blog-card {
      flex: 0 0 calc(50% - 20px); /* Two cards per row */
      max-width: 40%;
    }
  }

  @media (max-width: 480px) {
    .blog-card {
      flex: 0 0 calc(100% - 20px); /* One card per row */
      max-width: 40%;
    }
  }
</style>

