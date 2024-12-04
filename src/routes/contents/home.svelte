<script>
    import VideoPlayer from "./VideoPlayer.svelte";
    import Slider from './Slider.svelte';

</script>

<VideoPlayer/>


<Slider 
  slides={[
    { 
      src: "https://i.pinimg.com/236x/cb/da/01/cbda011ae0b5c56143e3cf9a516fb559.jpg", 
      alt: "Image 1", 
      title: "Explore astrophysics the dhRuVa way!", 
      description: "Head to the blog section to catch up with the latest happenings!", 
      text: "A take on the Universe in our way where persepctives meet and opinions grow",
      link: "/blogs" 
    },
    { 
      src: "https://i.pinimg.com/564x/35/37/10/353710a253ff533d2e4b1cc8c945ec3b.jpg", 
      alt: "Image 2", 
      title: "Research Divison at Team Dhruva", 
      description: "Greetings from the team", 
      text: "Meet the Team!!",
      link: "/team" 
    },
    
  ]}
/>