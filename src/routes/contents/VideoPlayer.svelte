<script>
    // Import video file
    import rd from './rd.mp4';
  </script>
  
  <style>
    .video-container {
      height: 50vh; /* Full viewport height */
      overflow: hidden; /* Prevent overflow in x and y directions */
      position: relative;
    }
  
    .background-video {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 100vw; /* Ensure video fills the viewport width */
      height: 100vh; /* Ensure video fills the viewport height */
      object-fit: cover; /* Ensures video covers the container without overflow */
      transform: translate(-50%, -50%); /* Center the video */
      z-index: -1; /* Send video behind overlay content */
    }
  
    .overlay-content {
      display: flex;
      flex-direction: row;
      position: relative; /* For overlay content positioning */
      color: white; /* Text color */
      text-align: left;
      z-index: 1; /* Bring overlay content above video */
      padding: 20px;
      font-weight: bold;
      gap: 200px; /* Space between items */
    }
  
    /* Responsive styles */
    @media (max-width: 768px) {
      .overlay-content {
        flex-direction: column; /* Stack items vertically */
        gap: 20px; /* Reduce spacing */
        text-align: center; /* Center text for smaller screens */
        padding: 10px; /* Reduce padding */
      }
    }
  
    @media (max-width: 480px) {
      .overlay-content {
        font-size: 14px; /* Adjust font size for better readability */
      }
    }
  </style>
  
  
  <div class="video-container">
    <video
      autoplay
      muted
      class="background-video"
    >
      <source src={rd} type="video/mp4" />
      <source src="path/to/your/video.webm" type="video/webm" />
      Your browser does not support the video tag.
    </video>
    <div class="overlay-content">
      <!-- Add overlay content here -->
    </div>
  </div>
  