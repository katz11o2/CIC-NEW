<script>
    import { fade, fly, scale } from "svelte/transition";

    let selectedImage = null;
    let filterMonth = "";
    let filterYear = "";

    let images = [
        { src: "https://media.licdn.com/dms/image/v2/D5622AQHDDIEz2dTjEw/feedshare-shrink_800/B56ZXbAQVgGQAk-/0/1743136039443?e=1746662400&v=beta&t=dUiY4n4VOkm8KfASdo0iOF7etfC7bbE6GZwSxgkjM5Y", title: "CHOSS", description: "Description for Festival 1", month: "January", year: "2023" },
        { src: "https://media.licdn.com/dms/image/v2/D5622AQF_0MPMNCoevg/feedshare-shrink_800/B56ZXliZPAGoAg-/0/1743312760901?e=1746662400&v=beta&t=fPOXVk4CtjMKza7Okib409rD3jyVaMidCIwyg_GEuS0", title: "Ugadi", description: "Festival of Colors", month: "March", year: "2023" },
        { src: "https://media.licdn.com/dms/image/v2/D5622AQEtZQnf2U2RCg/feedshare-shrink_800/B56ZXqmT8XGUAk-/0/1743397671095?e=1746662400&v=beta&t=mdc4ID4ztdPvmAR2ZincCukcuiKP2t6MLyVoD-Ka9XM", title: "Eid", description: "Nine nights of dance and devotion", month: "October", year: "2022" },
        { src: "https://media.licdn.com/dms/image/v2/D5622AQEba7s6A0XRkA/feedshare-shrink_800/B56ZXGqQLlHEAk-/0/1742794725782?e=1746662400&v=beta&t=zH561HI_JYTEDHO4ALeUvl_rbjZsnSMHunF_lBxHCus", title: "Workshop", description: "Ganpati Bappa Morya", month: "September", year: "2022" },
        { src: "https://media.licdn.com/dms/image/v2/D5622AQHEh8cS-XSxNQ/feedshare-shrink_800/B56ZWtsgJWHQAg-/0/1742375882972?e=1746662400&v=beta&t=lOEwaZca6OYOp8Nlbymx-KOQHcO3VioCiMLToKcj6Jk", title: "Awarness Event", description: "Festival of Lights", month: "November", year: "2023" },
        { src: "https://media.licdn.com/dms/image/v2/D5622AQE1j4wmJhht_g/feedshare-shrink_800/B56ZWncf4BHEAg-/0/1742271026656?e=1746662400&v=beta&t=6XFxVtEl0VMAXF3ESGRTFtmXOEh68H9-1CAIqsUVpp4", title: "Talk Session", description: "Harvest Festival of Tamil Nadu", month: "January", year: "2024" }
    ];

    function openImage(image) {
        selectedImage = image;
    }

    function closeImage() {
        selectedImage = null;
    }
</script>

<main class="container mx-auto p-8 bg-gradient-to-b from-indigo-600 to-purple-500 min-h-screen font-sans text-gray-100">
    <div class="text-center mb-12">
        <h1 class="text-6xl font-extrabold text-white drop-shadow-lg mb-4">Gallery</h1>
        <p class="text-lg text-gray-200">Explore our events and festivals through a curated gallery.</p>
    </div>

    <div class="flex justify-center gap-8 mb-8">
        <select bind:value={filterMonth} class="p-3 border-2 border-gray-300 rounded-lg text-gray-900 bg-white shadow-md focus:ring-2 focus:ring-indigo-500 transition-all">
            <option value="">Filter by Month</option>
            {#each ["January", "March", "September", "October", "November"] as month}
                <option value={month}>{month}</option>
            {/each}
        </select>
        <select bind:value={filterYear} class="p-3 border-2 border-gray-300 rounded-lg text-gray-900 bg-white shadow-md focus:ring-2 focus:ring-indigo-500 transition-all">
            <option value="">Filter by Year</option>
            {#each ["2022", "2023", "2024"] as year}
                <option value={year}>{year}</option>
            {/each}
        </select>
    </div>

    <div class="grid gap-8 grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
        {#each images as image (image.src)}
            {#if (!filterMonth || image.month === filterMonth) && (!filterYear || image.year === filterYear)}
                <div 
                    class="relative overflow-hidden rounded-lg shadow-2xl cursor-pointer transition-transform duration-300 transform hover:scale-105 hover:shadow-xl bg-white p-5"
                    in:fade={{ duration: 400 }}
                    on:click={() => openImage(image)}
                >
                    <img 
                        src={image.src} 
                        alt={image.title} 
                        class="w-full h-52 object-cover rounded-lg transition-all duration-300 hover:opacity-90"
                        loading="lazy"
                    />
                    <div class="absolute bottom-0 w-full bg-gradient-to-t from-black to-transparent p-3 text-center text-white font-bold text-lg">
                        {image.title}
                    </div>
                </div>
            {/if}
        {/each}
    </div>

    {#if selectedImage}
        <div 
            class="fixed inset-0 bg-black bg-opacity-80 flex items-center justify-center z-50 p-6 backdrop-blur-md" 
            on:click={closeImage} 
            transition:fade
        >
            <div class="bg-white p-8 rounded-2xl shadow-xl relative max-w-4xl w-full border-4 border-indigo-600 transform scale-105 hover:scale-110 transition-all duration-300"
                transition:fly={{ y: 20, duration: 300 }}
                on:click|stopPropagation
            >
                <button 
                    on:click={closeImage} 
                    class="absolute top-3 right-3 text-gray-700 text-3xl hover:text-red-600 focus:outline-none"
                >
                    &times;
                </button>
                <img src={selectedImage.src} alt={selectedImage.title} class="w-full rounded-lg shadow-md mb-4" />
                <h2 class="text-4xl font-semibold text-gray-900 text-center">
                    {selectedImage.title}
                </h2>
                <p class="text-gray-600 text-center mt-3 text-lg">{selectedImage.description}</p>
            </div>
        </div>
    {/if}
</main>

<style>
    main {
        min-height: 100vh;
        max-width: 1280px;
    }
    
    .container {
        max-width: 1320px;
        min-height: 100vh;
    }

    /* Added styles for responsiveness */
    @media (max-width: 768px) {
        main {
            padding: 4rem 1rem;
        }
        
        .container {
            padding: 2rem;
        }
    }
</style>
