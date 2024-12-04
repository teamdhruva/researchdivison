<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    export let title = "Chapter Title";
    export let detail="Chapter detail"
    export let images = [];

    function handleClick() {
        dispatch('click', images); // Emit click event with images
    }
</script>

<style>
   .chapter-card {
    background-color: black;
    color: white;
    padding: 5px;
    border-radius: 10px;
    border: 2px solid white; /* White border */
    cursor: pointer;
    transition: transform 0.3s;
    width: 1200px;
    height: 70px; /* Set the desired height */
    display: flex; /* Align content properly */
    align-items: center; /* Center content vertically */
    
}

.chapter-card:hover {
    transform: scale(1.05);
}

.text-container {
    display: flex;
    flex-direction: column; /* Stack title and detail vertically */
    justify-content: center; /* Center text vertically */
}



.detail {
    color: white;
    font-size: 16px; /* Keep detail font size */
    margin-top: 0; /* Ensure no additional top margin */
}

        
    
</style>

<div class="chapter-card" on:click={handleClick}>
    <div class="text-container">
    <h3>{title}</h3>
    <h4 class="detail">{detail}</h4>
</div>
</div>
