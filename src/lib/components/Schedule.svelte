<script>

    import dayjs from "dayjs";
    import { onMount } from "svelte";
    
    // declaring my variables 
    
    let currentDate = dayjs().format("YYYY-MM-DD");
    let currentTime = dayjs().format("HH:mm:ss"); 
    
    let randomHours = Math.floor(Math.random() * 24);
    let randomMinutes = Math.floor(Math.random() * 60); 
    let randomSeconds = Math.floor(Math.random() * 60);
    
    // these will be the randomized times for the made up "scheduled hockey games"
    
    let gameOne = dayjs().add(randomHours, +4, "hour").add(randomMinutes, "minute").add(randomSeconds, "second").format("HH:00:00");
    let gameTwo = dayjs().add(randomHours, "hour").add(randomMinutes, "minute").add(randomSeconds, "second").format("HH:00:00");
    let gameThree = dayjs().add(randomHours + 1, "hour").add(randomMinutes, "minute").add(randomSeconds, "second").format("HH:30:00");
    let gameFour = dayjs().add(randomHours + 3, "hour").add(randomMinutes, "minute").add(randomSeconds, "second").format("HH:15:00");
    let gameFive = dayjs().add(randomHours + 5, "hour").add(randomMinutes, "minute").add(randomSeconds, "second").format("HH:15:00");
    
    // function for currentTime to be updated, this should update the time every second and should work like an actual digital clock.
    
    const updateTime = () => {
        currentTime = dayjs().format("HH:mm:ss");
      };
    
      onMount(() => {
        
        const interval = setInterval(updateTime, 1000);
    
     });
      
    
    </script>
    
    <main>

    <h1>Regular Season Schedule</h1>
    
      
    <section>
  
  
    <!-- First set of games schedule -->
    
    <div>
      <h1>NBA Today's Games:</h1>
      <h1>{currentDate} {currentTime}</h1>
      <div>
        <p>Lakers vs Heat {gameTwo}</p>
        <p>Clippers vs Warriors {gameOne}</p>
        <p>Pistons vs Hornets {gameThree}</p>
      </div>
    </div>
    
    <!-- Second set of games schedule -->
    
    <div>
      <h1>Tomorrow's NBA Schedule</h1>
      <div>
        <p>Nuggets vs Hawks {gameFour}</p>
        <p>Raptors vs Knicks {gameFive}</p>
      </div>
    </div>

  
  </section>

</main>

  <style>
    main {
      margin: 0;
      font-family: Verdana, Geneva, Tahoma, sans-serif  ;
      
    }

    h1 {
      font-size: 2rem;
      text-align: center;
      color: black;
      margin-top: 20px;
    }

    section {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 20px;
    }

    div {
      
      border-radius: 8px;
      margin-bottom: 20px;
      padding: 20px;
      width: 80%;
      max-width: 600px;
      align-items: center;
    }

    p {
      font-size: 1.2rem;
      margin: 10px 0;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    /* Custom colors */
    h1, h1, p {
      color: black;
    }

    section div:nth-child(odd) {
      background-color: rgb(239, 109, 222);
    }

    section div:nth-child(even) {
      background-color: rgb(112, 239, 239);
    }
  </style>