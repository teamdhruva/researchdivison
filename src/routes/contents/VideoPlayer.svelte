<script>
  import laptop from "./laptop.mp4";
  import mobile from "./mobile.mp4";
  import { onMount } from "svelte";

  let videoSrc = laptop; // Default video source

  const updateVideoSrc = () => {
    videoSrc = window.innerWidth <= 768 ? mobile : laptop;
  };

  onMount(() => {
    updateVideoSrc(); // Set initial video source
    window.addEventListener("resize", updateVideoSrc); // Update on screen resize

    return () => {
      window.removeEventListener("resize", updateVideoSrc); // Cleanup event listener
    };
  });
</script>

<div class="video-container">
  <video autoplay muted class="background-video" aria-hidden="true">
    <source src={videoSrc} type="video/mp4" />
    <p>Your browser does not support the video tag. Please update your browser.</p>
  </video>
  <div class="overlay-content">
    <!-- Add overlay content here -->
  </div>
</div>

<style>
  .video-container {
    position: relative; /* Important for overlay positioning */
    height: 85vh;
    overflow: hidden; /* Prevents video overflow */
  }

  .background-video {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100vw;
    height: 100vh;
    object-fit: cover;
    transform: translate(-50%, -50%);
    z-index: -1;
  }

  .overlay-content {
    position: relative;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    color: white;
    text-align: left;
    z-index: 1;
    padding: 20px;
    font-weight: bold;
    gap: 200px;
  }

  /* Responsive styles */
  @media (max-width: 768px) {
    .overlay-content {
      flex-direction: column;
      text-align: center;
      gap: 20px;
      padding: 10px;
    }
  }

  @media (max-width: 480px) {
    .overlay-content {
      font-size: 14px;
    }
  }
</style>
