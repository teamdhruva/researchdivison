<script>
    import Blog from '../contents/Blog.svelte';
    import chapter1 from '../contents/blogs/ch1.md'

    const blogs = [
  {
    id: 1,
    title: "Understanding Svelte",
    author: "John Doe",
    description: "A guide to understanding the basics of Svelte.",
    chapters: [
      { id: 1, title: "Introduction", markdown: "# Introduction\nThis is the intro chapter." },
      { id: 2, title: "Getting Started", markdown: chapter1 },
      { id: 3, title: "Step1", markdown: chapter1 },
      { id: 4, title: "Step1", markdown: chapter1 },
      { id: 5, title: "Step1", markdown: chapter1 },
    ],
    nextChapterDate: "2024-12-31",
    image:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzjNHi24fSm5AkBnqbg7eUFzxpSP_Ok7sjqA&s",
    lastUpdated:'2-24-12-24',
  },
  {
    id: 2,
    title: "Advanced Svelte",
    author: "Jane Smith",
    description: "Delve into advanced Svelte concepts.",
    chapters: [
      { id: 1, title: "State Management", markdown: "# State Management\nUnderstanding state in Svelte." },
      { id: 2, title: "Animations", markdown: "# Animations\nHow to use animations in Svelte." }
    ],
    nextChapterDate: "2025-01-15",
    image:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzjNHi24fSm5AkBnqbg7eUFzxpSP_Ok7sjqA&s"
  },
  {
    id: 3,
    title: "Advanced Svelte",
    author: "Jane Smith",
    description: "Delve into advanced Svelte concepts.",
    chapters: [
      { id: 1, title: "State Management", markdown: "# State Management\nUnderstanding state in Svelte." },
      { id: 2, title: "Animations", markdown: "# Animations\nHow to use animations in Svelte." }
    ],
    nextChapterDate: "2025-01-15",
    image:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzjNHi24fSm5AkBnqbg7eUFzxpSP_Ok7sjqA&s"
  },
  {
    id: 4,
    title: "Advanced Svelte",
    author: "Jane Smith",
    description: "Delve into advanced Svelte concepts.",
    chapters: [
      { id: 1, title: "State Management", markdown: "# State Management\nUnderstanding state in Svelte." },
      { id: 2, title: "Animations", markdown: "# Animations\nHow to use animations in Svelte." }
    ],
    nextChapterDate: "2025-01-15",
    image:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzjNHi24fSm5AkBnqbg7eUFzxpSP_Ok7sjqA&s"
  },
];

</script>
<div>
    <h1>Dive into Amazing reads!!!</h1>
    <Blog {blogs} />
  </div>