<script>
    import { onMount } from "svelte";
  
    let fadeIn = false;
    function goToGoogle() {
    window.location.href = "https://engg.cambridge.edu.in/";
  }
    // Trigger fade-in animation after mount
    onMount(() => {
      fadeIn = true;
    });
  </script>
  
  <style>
    /* Global Styles */
    .flowchart {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    top: 100px;
    gap: 20px;
  }

  .button-box {
    background-color: white;
    color: black;
    padding: 10px 20px;
    border: 1px solid black;
    cursor: pointer;
    font-weight: bold;
    width: 250px;
    text-align: center;
    border-radius: 8px;
    transition: background 0.3s ease;
  }

  .button-box:hover {
    background-color: #ddd;
  }

  .connector {
    width: 2px;
    height: 30px;
    background-color: black;
  }


  .flowchart {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.row {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 40px; /* Space between Manager, HoD, and Scientist */
}

.connector {
  width: 2px;
  height: 30px;
  background-color: black;
}

.vertical {
  width: 2px;
  height: 30px;
  background-color: black;
  margin: 0 auto;
}

.button-box {
  background-color: white;
  color: black;
  padding: 10px 20px;
  border: 1px solid black;
  cursor: pointer;
  font-weight: bold;
  width: 250px;
  text-align: center;
  border-radius: 12px;
  transition: background 0.5s ease;
}

.button-box:hover {
  background-color: #d3c4eb;
}

  

  .row {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
  }

    :global(body) {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 200vh;
      font-family: "Poppins", sans-serif;
      background: linear-gradient(to left, #0b256c, #671da7);
      color: white;
      text-align: center;
      padding: 20px;
    }
  
    /* Main Container - Glassmorphism Effect */
    .container {
      max-width: 950px;
      padding: 10px;
      height: 100%;
      background: rgba(255, 255, 255, 0.2);  /* Slightly darker for better contrast */
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
      backdrop-filter: blur(15px);
      -webkit-backdrop-filter: blur(15px);
      border: 1px solid rgba(255, 255, 255, 0.3);
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 1s ease-out, transform 1s ease-out;
    }
  
    /* Animation Class */
    .fade-in {
      opacity: 1;
      transform: translateY(0);
    }
  

    .horizontal {
  width: 40px; /* Adjust width to your need */
  height: 2px;
  background-color: black;
  margin-top: 15px; /* Align properly with buttons */
}
    /* Logo Styling */
    .logo {
      width: 500px;
      position: relative;
      left: 170px;
      height: auto;
      margin-top: 20px;
      filter: drop-shadow(0px 5px 10px rgba(0, 0, 0, 0.2));
      transition: transform 0.3s ease-in-out;
    }
  
    .logo:hover {
      transform: scale(1.1);
    }
  
    /* Typography */
    h1 {
  font-size: 1.4rem;
  font-weight: 900;
  letter-spacing: 1.2px;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.4);
  margin-top: 20px; /* 👈 Added margin */
  font-family: 'Montserrat', sans-serif;
}

h2 {
  font-size: 1.4rem;
  font-weight: 600;
  opacity: 0.95;
  margin-top: 20px; /* 👈 Added margin */
  font-family: 'Montserrat', sans-serif;
}

p {
  font-size: 1.1rem;
  line-height: 1.8;
  text-align: justify;
  margin-top: 20px; /* 👈 Added margin */
  font-family: 'Merriweather', serif;
}

.msme-link {
    color: #f1f2f3; /* Default color */
    text-decoration: none; /* Optional: Removes underline */
    font-weight: bold;
    transition: color 0.3s ease-in-out;
  }

  .msme-link:hover {
    color: #2c1357; /* Change to any color you like */
    text-decoration: underline;
  }

  </style>
  
  <div class="container {fadeIn ? 'fade-in' : ''}">
    <h1>The Cambrian Incubation Centre (CIC)</h1>
    <h2>Encouraging Technological Innovation & Entrepreneurship</h2>
    <p>The Cambrian Incubation Centre (CIC) is a smart initiative, established by <a href="https://engg.cambridge.edu.in/" target="_blank" class="msme-link">Cambridge Institute of Technology</a>,  Bangalore, to create a vibrant ecosystem that encourages technological innovation leading to entrepreneurship and growth. Its primary objective is to provide a supportive environment to innovation-hungry <a href="https://msme.gov.in/" target="_blank" class="msme-link">MSMEs</a> to the extent possible and permissible. It fosters creation of a collaborative environment where students (potential entrepreneurs), academic staff (as mentors), and industry experts, especially from <a href="https://msme.gov.in/" target="_blank" class="msme-link">MSMEs</a>, can connect, share knowledge, and grow together with eligible scheme support from the <a href="https://msme.gov.in/" target="_blank" class="msme-link"> Ministry of MSME (Govt of India).</a> </p>
    <p>The creation of a dedicated Centre is the outcome of recognition of Cambridge Institute of Technology (Bangalore) as a <a href="https://www.dcmsme.gov.in/" target="_blank" class="msme-link">Host Institution</a>, by the Office of the Development Commissioner - MSME , <a href="https://msme.gov.in/" target="_blank" class="msme-link"> Ministry of MSME</a>, Govt of India. This Centre is also supported by the <a href="https://msme.gov.in/" target="_blank" class="msme-link">MSME</a> Centre of Excellence <a href="https://www.dcmsme.gov.in/" target="_blank" class="msme-link">(DCMSME) </a> IISc, Bangalore. This Centre would provide several facilities like Incubation Space (having office space, meeting rooms, internet, etc), Mentorship (connect with learned faculty), exposure to cutting-edge technologies (through participation in events like awareness programs and workshops), laboratories (for experimentation, etc).</p>


    <div class="flowchart">
      <!-- Top - Chairman -->
      <button class="button-box chairman" on:click={goToGoogle}>
        Chairman / CEO / Principal<br>CIT - Bangalore
      </button>
      
      <div class="connector vertical"></div>
    
      <div class="row">
        <!-- Left - Manager -->
        <div class="column">
          <button class="button-box" on:click={goToGoogle}>
            Manager (CHOSS)<br>CIT - Bangalore
          </button>
        </div>
        <div class="horizontal"></div>
        <!-- Center - HoD -->
        <div class="column">
          <button class="button-box hod" on:click={goToGoogle}>
            HoD (Incubation)<br>CIT - Bangalore
          </button>
        </div>
    
        <div class="horizontal"></div>
        <!-- Right - Project Scientist -->
        <div class="column">
          <button class="button-box" on:click={goToGoogle}>
            Project Scientist (MSME)<br>Bangalore
          </button>
        </div>
      </div>
    
      <div class="connector vertical"></div>
    
      <!-- Bottom - All HoDs -->
      <button class="button-box" on:click={goToGoogle}>
        All HoDs<br>CIT - Bangalore
      </button>
    </div>
    
   

  </div>
  