<script lang="ts">
    import TeamMember from "$lib/TeamMember.svelte"; // Adjust the path as needed
  
    const members = [
      { name: "Krishna", role: "Astrophysicist", image: null },
      { name: "Sunil", role: "Particle Physicist", image: null },
      { name: "Akash", role: "Particle Physicist", image: null },
      { name: "Harshhitha", role: "Particle Physicist", image: null },
      { name: "Prarthana", role: "Particle Physicist", image: null },
      { name: "Nitya", role: "Particle Physicist", image: null },
      { name: "Khushi", role: "Particle Physicist", image: null },
      { name: "Manohara", role: "Particle Physicist", image: null },
      { name: "Atharva", role: "Particle Physicist", image: null },
      { name: "Manav", role: "Particle Physicist", image: null },
      { name: "Shrirang", role: "Particle Physicist", image: null },
      { name: "Srujan", role: "Particle Physicist", image: null },
      { name: "Aryan", role: "Particle Physicist", image: null },
      { name: "Pratiksha", role: "Particle Physicist", image: null },
      { name: "Rutvik", role: "Particle Physicist", image: null },
      { name: "Spoorthy", role: "Particle Physicist", image: null },
      { name: "Vibha", role: "Particle Physicist", image: null },
      { name: "Shrish", role: "Particle Physicist", image: null },
      { name: "Aneesh", role: "Particle Physicist", image: null },
      { name: "Amruta", role: "Particle Physicist", image: null },
      { name: "Deepthi", role: "Particle Physicist", image: null },
      { name: "Shashank", role: "Particle Physicist", image: null }

      // Add more members as needed
    ];
  </script>
  
  <style>
    .team {
      display: flex;
      flex-wrap: wrap; /* Allow wrapping */
      justify-content: center; /* Center-align items */
      padding: 20px; /* Optional padding around the container */
    }

    h1 {
    color: #007bff; /* Blue color */
    font-weight: bold; /* Bold text */
    text-align: center; /* Center text */
    margin-bottom: 20px; /* Space below the heading */
    
  }
  </style>
  <h1>Team</h1>
  <div class="team">
    
    {#each members as member}
      <TeamMember {member} />
    {/each}
  </div>
  