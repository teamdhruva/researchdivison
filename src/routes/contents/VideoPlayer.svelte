<script>
    // Import video file
    import rd from './rd.mp4';
  </script>
  
  <style>
    .video-container {
      /*position: relative;  To position overlay content */
      height: 100vh; /* Full viewport height */
      overflow: hidden;  /*Hide overflow */
    }
  
    .background-video {
      position: absolute;
      top: 50%;
      left: 50%;
      min-width: 100%; /* Ensure video covers the entire container */
      min-height: 100%;
      width: auto; /* Maintain aspect ratio */
      height: auto; /* Maintain aspect ratio */
      transform: translate(-50%, -50%); /* Center the video */
      z-index: -1; /* Send video behind overlay content */
    }
  
    .overlay-content {
      display: flex;
      flex-direction: row;
      position: relative; /* For overlay content positioning */
      color: white; /* Text color */
      text-align: left; /* Center text */
      z-index: 1; /* Bring overlay content above video */
      padding: 20px;
      font-weight: bold;
      gap: 200px; /* Space between items */
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
      
    </div>

  </div>
  