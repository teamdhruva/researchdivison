<script>
    import MangaCard from './MangaCard.svelte';
    import MangaDetail from './MangaDetail.svelte';
    import ImageViewer from './ImageViewer.svelte';
    import cover from '../resource/Exocover.png';
    import BlogCard from './BlogCard.svelte';
    let showDetail = false;
    let showImageViewer = false;
    let selectedManga = null;
    let imagesToShow = [];

    const mangas = [
        {
            title: "History of Space Exploration",
            imageUrl: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzjNHi24fSm5AkBnqbg7eUFzxpSP_Ok7sjqA&s",
            description: "Overview: Countdown…T minus…3…2…1 and you are now in for a trip down the memory lane that will make you admire the efforts and brilliance that has gone into the space exploration missions. The world and our understanding of it would’ve been much different had mankind not started to explore the universe. This thought must have occurred to you at some point in time,”How did it all begin??!!”.Amidst the war stricken world that was divided by different and conflicting beliefs, dawned the new face of the world. This blog tries to chronicle the most fascinating episodes of space exploration and presents a timeline of our tryst with the mighty universe!",
            authors:"Authors: Prarthana and Atharva",
            chapters: [
                {
                    title: "Chapter 1",
                    detail:"Cruising into the unexplored(1940-60)",
                    images: ["https://teamdhruva.netlify.app/static/media/Page1.6db92d27f822cfb69fb1.png", "https://teamdhruva.netlify.app/static/media/Page2.327314d07b4fd5924e4c.png","https://teamdhruva.netlify.app/static/media/Page3.5b5dd3f2362c880e9782.png"]
                },
                {
                    title: "Chapter 2",
                    detail:"Tryst with Moon(1960-1970)",
                    images: ["https://teamdhruva.netlify.app/static/media/Page4.c972f51df1b83fe9e17d.png", "https://teamdhruva.netlify.app/static/media/Page5.fed895b66764a2fb2e7d.png"]
                },
                {
                    title: "Chapter 3",
                    detail:"Understanding our neighbours better(1970-90)",
                    images: ["https://teamdhruva.netlify.app/static/media/Page4.c972f51df1b83fe9e17d.png", "https://teamdhruva.netlify.app/static/media/Page5.fed895b66764a2fb2e7d.png"]
                },
                {
                    title: "Chapter 4",
                    detail:"A harbour to sail in the stellar winds(1990-2000)",
                    images: ["https://teamdhruva.netlify.app/static/media/Page4.c972f51df1b83fe9e17d.png", "https://teamdhruva.netlify.app/static/media/Page5.fed895b66764a2fb2e7d.png"]
                }
            ]
        },
        {
            title: "Exoplanets: Chasing the Aliens",
            imageUrl: cover,
            description: "Overview: Exploring the world beyond ours",
            authors:"Khushi and Pratiksha",
            chapters: [
                {
                    title: "Chapter 1",
                    detail:"What are Exoplanets?",
                    images: []
                },
                {
                    title: "Chapter 2",
                    detail:"Do you think all the exoplnets are similar?",
                    images: []
                },
                {
                    title: "Chapter 3",
                    detail:"Techniques used for detecting exoplanets",
                    images: []
                },
                {
                    title: "Chapter 4",
                    detail:"The fascinating alien worlds",
                    images: []
                },
                {
                    title: "Chapter 5",
                    detail:"Largest batch of earth-sized exoplanets",
                    images: []
                }

            ]
        },
        {
            title: "Beyond Earth: Life among stars",
            imageUrl: "https://t3.ftcdn.net/jpg/04/43/88/94/360_F_443889444_IxDN8BRSaxXsPzKXZ3x5SVsC51BsVFgy.jpg",
            description: "Overview: Exploring the world beyond ours",
            authors:"Khushi and Pratiksha",
            chapters: [
                {
                    title: "Chapter 1",
                    detail:"What are Exoplanets?",
                    images: []
                },
                {
                    title: "Chapter 2",
                    detail:"Do you think all the exoplnets are similar?",
                    images: []
                },
                {
                    title: "Chapter 3",
                    detail:"Techniques used for detecting exoplanets",
                    images: []
                },
                {
                    title: "Chapter 4",
                    detail:"The fascinating alien worlds",
                    images: []
                },
                {
                    title: "Chapter 5",
                    detail:"Largest batch of earth-sized exoplanets",
                    images: []
                }

            ]
        }

        // Add more manga objects here...
    ];

    function showMangaDetail(manga) {
        selectedManga = manga;
        showDetail = true;
    }

    function handleBack() {
        showDetail = false;
        selectedManga = null;
    }

    function openImageViewer(images) {
        imagesToShow = images;
        showImageViewer = true;
    }

    function closeImageViewer() {
        showImageViewer = false;
        imagesToShow = [];
    }


</script>

<style>

    
    .manga-list {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }

    .Head {
        color: #007bff; /* Blue color */
        font-size: 24px; /* Font size */
        font-weight: bold; /* Bold text */
        text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.4); /* Shadow for depth */
        letter-spacing: 1px; /* Spacing between letters */
        line-height: 1.5; /* Line height */
    }

    .intro{
        display: flex;
        align-items: center;
        justify-content: center;
        color: white; /* Blue color */
        font-size: 18px; /* Font size */
        font-weight: bold; /* Bold text */
        text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.4); /* Shadow for depth */
        letter-spacing: 1px; /* Spacing between letters */
        line-height: 1.5; /* Line height */ 
    }

    

  h1 {
    font-size: 2.5em;
    margin-bottom: 20px;
    color: #333;
  }
</style>


<h1 class="Head">Dive into amazing reads!!</h1>
<h3 class="intro">A take on the Universe in our way where persepctives meet and opinions grow</h3>

{#if showImageViewer}
    <ImageViewer 
        images={imagesToShow} 
        onClose={closeImageViewer} 
    />
{:else if showDetail}
    <MangaDetail 
        title={selectedManga.title} 
        description={selectedManga.description}
        authors={selectedManga.authors}
        imageUrl={selectedManga.imageUrl} 
        chapters={selectedManga.chapters} 
        onBack={handleBack} 
        onOpenImageViewer={openImageViewer} 
    />
{:else}
    <div class="manga-list">
        {#each mangas as manga}
            <MangaCard 
                title={manga.title} 
                imageUrl={manga.imageUrl} 
                onClick={() => showMangaDetail(manga)} 
            />
        {/each}
    </div>
{/if}

