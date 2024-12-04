<script>
    // You can modify the image source here or bind it dynamically
    let imageSrc = "/path/to/your/image.jpg"; // Replace with the actual image path
</script>

<style>
    .Main {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center; /* Align text and images center */
    }
  
    .Head {
        color: #007bff; /* Blue color */
        font-size: 24px; /* Font size */
        font-weight: bold; /* Bold text */
        text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.4); /* Shadow for depth */
        letter-spacing: 1px; /* Spacing between letters */
        line-height: 1.5; /* Line height */
    }
  
    .Text {
        padding-left: 20px;
        justify-content: center;
        font-size: 18px;
        color: white;
        font-weight: bold;
        letter-spacing: 1px; /* Spacing between letters */
        line-height: 1.5; /* Line height */
    }
  
    .vision {
        color: #007bff; /* Blue color */
        font-size: 24px; /* Font size */
        font-weight: bold; /* Bold text */
        text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.4); /* Shadow for depth */
        letter-spacing: 1px; /* Spacing between letters */
        line-height: 1.5; /* Line height */
    }
  
    .vision-text {
        display: flex;
        flex-direction: column;
        padding-left: 20px;
        justify-content: center;
        font-size: 18px;
        color: white;
        font-weight: bold;
        letter-spacing: 1px; /* Spacing between letters */
        line-height: 1.5; /* Line height */
    }

    .image-container {
        display: flex;
        flex-direction: row;
        margin: 20px 0;
        text-align: center;
    }

    .image-container img {
        width: 100%; /* Make the image responsive */
        max-width: 500px; /* You can adjust the max width */
        height: 50%;
        border-radius: 8px; /* Optional: Add rounded corners */
    }
</style>

<div class="Main">
    <!-- Image Section -->
    <div class="image-container">
        <img src="https://i.pinimg.com/736x/c6/9b/d3/c69bd3ab92584b8065edf60479df5897.jpg" alt="Indian Astrophysics" />
        <img src="https://i.pinimg.com/736x/c6/9b/d3/c69bd3ab92584b8065edf60479df5897.jpg" alt="Indian Astrophysics" />
        <img src="https://i.pinimg.com/736x/c6/9b/d3/c69bd3ab92584b8065edf60479df5897.jpg" alt="Indian Astrophysics" />
    </div>
    <h1 class="Head">Unveil secrets of Indian Astrophysics</h1>
  
    <p class="Text"> 
        Indian astrophysics has made significant strides over the years, with contributions ranging from theoretical advancements to observational discoveries.
    </p>
  
    <h1 class="vision">Upcoming Review Papers</h1>
    <p class="vision-text">
        Indian Calendar
    </p>
    <p class="vision-text">Computational research using Stellarium</p>
</div>
