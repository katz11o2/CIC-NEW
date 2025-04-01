<script>
    let labs = [
        { name: "POC: Mr. Nithin - 9916455287", img: "https://media.licdn.com/dms/image/v2/D560BAQHJCjL_3y1kUQ/company-logo_200_200/company-logo_200_200/0/1734347483383/galactic_3d_logo?e=2147483647&v=beta&t=61aU_boi2QFSpzf0jfH3NHPVaq2GDNYoQFSt8sQPczM"},
        { name: "POC: Mr. John - 9916455286", img: "https://media.licdn.com/dms/image/v2/D560BAQE41py0zEa4VA/company-logo_200_200/company-logo_200_200/0/1684866831757?e=2147483647&v=beta&t=uqG2kFA8kbHC08D8-0_f6Zot9tgmwsYVxZfMeE-zz0g", poc: "Jane Smith", contact: "+91 87654 32109", location: "London, UK" },
        { name: "POC: Mr. David - 9916455286", img: "https://www.sammyfans.com/wp-content/uploads/2022/01/Samsung-Innovation-Campus.jpg", poc: "Alice Brown", contact: "+91 99988 77665", location: "Sydney, Australia" },
        { name: "POC: Mr. Varun - 9916455286", img: "https://media.licdn.com/dms/image/v2/D560BAQF2y3Yx7-VJGQ/company-logo_200_200/company-logo_200_200/0/1665363849767/samsungsemiconductor_logo?e=2147483647&v=beta&t=SWfEtNFdoYtGSbjc_kmK1wu_LlOKkwS4TLB5fRVyVow", poc: "David Lee", contact: "+91 88877 66554", location: "Toronto, Canada" },
        { name: "POC: Mr. Shilpa - 9916455286", img: "https://yt3.googleusercontent.com/2eI1TjX447QZFDe6R32K0V2mjbVMKT5mIfQR-wK5bAsxttS_7qzUDS1ojoSKeSP0NuWd6sl7qQ=s900-c-k-c0x00ffffff-no-rj", poc: "Emma Watson", contact: "+91 77766 55443", location: "Berlin, Germany" },
        { name: "POC: Mr. Kartick - 9916455286", img: "data:image/jpeg;base64,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", poc: "Robert Smith", contact: "+91 77766 55443", location: "Paris, France" },
        { name: "POC: Mr. Thiru - 9916455286", img: "https://i.pinimg.com/originals/01/ca/da/01cada77a0a7d326d85b7969fe26a728.jpg", poc: "Olivia Brown", contact: "+91 66655 44332", location: "Rome, Italy" },
        { name: "POC: Mr. Syed - 9916455286", img: "https://yt3.googleusercontent.com/ytc/AIdro_mInmR-_Ufvk4rkLRy1QiOyXXF7SB6yfJHWUloZ0wl5U8c=s900-c-k-c0x00ffffff-no-rj", poc: "Michael Scott", contact: "+91 55544 33221", location: "Dubai, UAE" },
        { name: "POC: Mr. Mohan - 9916455286", img: "https://yt3.googleusercontent.com/btm1_PK-7VRUr9GY2D0UV_2XfbUZPBjghyptjSO1crsfN86HyTYDWPmUbq7JxC3H0Lxe_s067nA=s900-c-k-c0x00ffffff-no-rj", poc: "Rachel Green", contact: "+91 44433 22111", location: "Los Angeles, USA" },
      
    ];
</script>

<main class="container mx-auto p-6">
    <h1 class="text-3xl font-bold text-center text-gray-800 mb-6">Our Laboratories</h1>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
        {#each labs as lab (lab.name)}
            <div class="card-container">
                <div class="card">
                    <div class="card-front">
                        <img src={lab.img} alt={lab.name} class="w-full h-full object-cover rounded-lg" />
                    </div>
                    <div class="card-back">
                        <div class="info">
                           
                        </div>
                    </div>
                    <div class="card-flip-text">
                        <span class="lab-name">{lab.name}</span>
                    </div>
                </div>
            </div>
        {/each}
    </div>
</main>

<style>
    main {
        max-width: 1200px;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        gap: 20px;
    }

    :global(body) {
        margin: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 200vh;
        font-family: "Poppins", sans-serif;
        background: linear-gradient(to left, #142d6c, #671da7);
        color: white;
        text-align: center;
        padding: 20px;
    }

    .card-container {
        perspective: 1000px;
    }

    .card {
        width: 100%;
        height: 300px;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        transform-style: preserve-3d;
        transition: transform 0.6s ease-in-out, box-shadow 0.3s ease-in-out;
        border-radius: 12px;
        overflow: hidden;
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
    }

    h1 {
   color: aliceblue;
    }
    .card-front, .card-back, .card-flip-text {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        
        bottom: 0;
        backface-visibility: hidden; /* Ensures that the back side is hidden when flipped */
        transition: all 0.6s ease;
    }

    .card-front {
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        
    }

    .card-back {
    background: #2c3e50;
    color: black;
    transform: rotateY(180deg); /* Flip the card */
    padding: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-direction: column;
    /* Remove additional rotation or transform for the text */
}

.card-container:hover .card {
    transform: rotateY(180deg); /* Flip the entire card */
}

.card-container:hover .card-front {
    transform: scale(1.05); /* Optional scaling on hover */
}

    .card-flip-text {
        background-color: rgb(251, 248, 254);
        display: flex;
        justify-content: center;
        align-items: center;
        color: black;
        font-size: 1rem;
        
        font-weight: bold;
        font-family:Verdana, Geneva, Tahoma, sans-serif;
        opacity: 0;
        transition: opacity 0.7s ease;
    }

    .card-container:hover .card {
        transform:  rotate(0deg); 
        box-shadow: 0 20px 40px rgba(0, 0, 0, 0.25);
    }

    .card-container:hover .card-flip-text {
        opacity: 9;
        
    }

    .card-container:hover .card-front {
        transform: scale(6.05);
    }

    .info h2 {
        font-size: 1.5rem;
        font-weight: bold;
        margin-bottom: 10px;
    }

    .info p {
        margin: 5px 0;
        font-size: 0.875rem;
    }

    @media (max-width: 768px) {
        .grid {
            grid-template-columns: repeat(2, 1fr);
        }

        .card {
            height: 250px;
        }
    }

    @media (max-width: 480px) {
        .grid {
            grid-template-columns: 1fr;
        }

        .card {
            height: 200px;
        }
    }
</style>
