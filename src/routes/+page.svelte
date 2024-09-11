<script>
  export let data

  let strumTrigger
  let mySound
  let current = 0;

  function playSound(mySound) {
    mySound.play();
  }

  function showInfo() {
    current = (current + 1) % 7;
    return current;
  }
</script>

<svelte:head>
  <title>Visitekaartje</title>
</svelte:head>

<h1>{data.person.name}'s visitekaartje</h1>

<main>
  <section>
    <p class:hide={current != 0} class:show={current === 0}>Strum om meer over mij uit te vinden.</p>
    <p class:hide={current != 1} class:show={current === 1}>{data.person.name} {data.person.surname}</p>
    <p class:hide={current != 2} class:show={current === 2}>{data.person.nickname}</p>
    <div class:hide={current != 3} class:show={current === 3}>
      <a href="{data.person.github_handle}">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 496 512" width="20px" height="20px">
          <path d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3 .3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5 .3-6.2 2.3zm44.2-1.7c-2.9 .7-4.9 2.6-4.6 4.9 .3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3 .7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3 .3 2.9 2.3 3.9 1.6 1 3.6 .7 4.3-.7 .7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3 .7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3 .7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z"/>
        </svg>
        Github
      </a>
    </div>
    <div class:hide={current != 4} class:show={current === 4}>
      <img src="{data.person.avatar}" alt="baby groot" width="90px" height="90px">
    </div>
    <p class:hide={current != 5} class:show={current === 5}>2D</p>
    <p class:hide={current != 6} class:show={current === 6}>{data.person.bio}</p>
  </section>
  
  <svg class="guitarSVG" viewBox="0 0 1256 3200">
    <filter id="f2" x="-100%" y="-100%" width="300%" height="300%">
        <feOffset result="offOut" in="SourceAlpha" dx="0" dy="-33" />
        <feBlend in="SourceGraphic" in2="blurOut" mode="normal" />
      </filter>
    <g class="guitarBody">
      <path d="M 626 1600 C 1135 1600 1116 1738 1055 2176 C 1035 2323 1721 3176 622 3194 C -465 3176 221 2323 201 2176 C 140 1738 121 1600 630 1600 Z" fill="var(--body2)" transform="translate(0 -50)"/>
      <path d="M 626 1600 C 1135 1600 1116 1738 1055 2176 C 1035 2323 1721 3176 622 3194 C -465 3176 221 2323 201 2176 C 140 1738 121 1600 630 1600 Z" fill="var(--body)"/>
      <circle cx="628" cy="2072" r="156" fill="var(--sound-hole)" />
      <circle cx="628" cy="2072" r="162" fill="none" stroke="var(--sound-hole-ring)" stroke-width="5" />
      <path d="M 390 2490 H 862 V 2570 H 798 Q 626 2635 454 2570 H 390 Z" fill="var(--bridge-head)"/>
      <path d="M484 2527 L 772 2513" stroke-width="10" stroke="var(--nut)" stroke-linecap="round" />
    </g>
    
    <g class="guitarNeck">
      <path d="M 530 1910 H 722 V 462 H 530 V 1910" fill="var(--fretboard)" />
      <path d="M 462 345 L 562 325 M 462 231 L 562 211 M 462 112 L 562 92 M 790 345 L 690 325 M 790 231 L 690 211 M 790 112 L 690 92" stroke="var(--tuners)" stroke-width="14"/>
      <g class="dots" fill="var(--fretdots)">
        <circle cx="626" cy="934" r="10" />
        <circle cx="575" cy="1102" r="10" />
        <circle cx="677" cy="1102" r="10" />
        <circle cx="626" cy="1259" r="10" />
        <circle cx="575" cy="1456" r="10" />
        <circle cx="677" cy="1456" r="10" />
        <circle cx="626" cy="1625" r="10" />
        <circle cx="626" cy="1720" r="10" />
      </g>
      <g class="tuners" fill="var(--tuners)">
        <circle cx="462" cy="345" r="26" />
        <circle cx="462" cy="231" r="26" />
        <circle cx="462" cy="112" r="26" />
        <circle cx="790" cy="345" r="26" />
        <circle cx="790" cy="231" r="26" />
        <circle cx="790" cy="112" r="26" />
      </g>
      <path d="M 530 458 H 722 Q 745 414 746 400 L 766 60 Q 769 7 717 7 H 535 Q 487 7 490 60 L 506 400 Q 507 414 530 458 Z" fill="var(--bridge-head)"/>
      <path d="M 528 455 H 724" stroke-width="14" stroke="var(--nut)" stroke-linecap="round" />
      <path class="frets" d="M 530 580 H 722 M 530 695 H 722 M 530 791 H 722 M 530 891 H 722 M 530 976 H 722 M 530 1064 H 722 M 530 1145 H 722 M 530 1223 H 722 M 530 1293 H 722 M 530 1364 H 722 M 530 1426 H 722 M 530 1485 H 722 M 530 1545 H 722 M 530 1600 H 722 M 530 1648 H 722 M 530 1696 H 722 M 530 1744 H 722 M 530 1785 H 722 M 530 1825 H 722 M 530 1866 H 722" stroke-width="5" stroke="var(--frets)" stroke-linecap="round" />
    </g>
    <g class="strings" fill="none" stroke-width="7" stroke="var(--strings)">
      <path class="string1" d="M 542 2560 Q 542 1507 542 455 L 567 325">
        <animate class="string" attributeName="d" values="M 542 2560 Q 542 1507 542 455 L 567 325" begin="indefinite" dur="0.5s" repeatCount="none" />
      </path>
      <path class="string2" d="M 576 2559 Q 576 1507 576 455 L 567 211">
        <animate class="string" attributeName="d" values="M 576 2559 Q 576 1507 576 455 L 567 211" begin="indefinite" dur="0.5s" repeatCount="none" />
      </path>
      <path class="string3" d="M 610 2557 Q 610 1507 610 455 L 567 92">
        <animate class="string" attributeName="d" values="M 610 2557 Q 610 1507 610 455 L 567 92" begin="indefinite" dur="0.5s" repeatCount="none" />
      </path>
      <path class="string4" d="M 642 2555 Q 642 1507 642 455 L 685 92">
        <animate class="string" attributeName="d" values="M 642 2555 Q 642 1507 642 455 L 685 92" begin="indefinite" dur="0.5s" repeatCount="none" />
      </path>
      <path class="string5" d="M 676 2553 Q 676 1507 676 455 L 685 211">
        <animate class="string" attributeName="d" values="M 676 2553 Q 676 1507 676 455 L 685 211" begin="indefinite" dur="0.5s" repeatCount="none" />
      </path>
      <path class="string6" d="M 710 2550 Q 710 1507 710 455 L 685 325">
        <animate class="string" attributeName="d" values="M 710 2550 Q 710 1507 710 455 L 685 325" begin="indefinite" dur="0.5s" repeatCount="none" />
      </path>
    </g>
    <g class="stringDots" fill="var(--tuners)">
      <g class="topDots">
        <circle cx="562" cy="325" r="20" />
        <circle cx="562" cy="211" r="20" />
        <circle cx="562" cy="92" r="20" />
        <circle cx="690" cy="325" r="20" />
        <circle cx="690" cy="211" r="20" />
        <circle cx="690" cy="92" r="20" />
      </g>
      <g class="bottomDots">
        <circle cx="542" cy="2560" r="12" />
        <circle cx="576" cy="2559" r="12" />
        <circle cx="610" cy="2557" r="12" />
        <circle cx="645" cy="2555" r="12" />
        <circle cx="678" cy="2553" r="12" />
        <circle cx="712" cy="2550" r="12" />
      </g>
    </g>
    <rect class="guitarPick" height="100" width="100" fill="rgba(255,255,255,0)" x="0" y="0" />
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <g fill="rgba(0,0,255,0)" on:click={playSound(mySound)} on:click={showInfo}>
      <rect bind:this={strumTrigger} height="2112" width="64" x="508" y="448" />
      <rect bind:this={strumTrigger} height="2112" width="64" x="546" y="448" />
      <rect bind:this={strumTrigger} height="2112" width="64" x="578" y="448" />
      <rect bind:this={strumTrigger} height="2112" width="64" x="610" y="448" />
      <rect bind:this={strumTrigger} height="2112" width="64" x="646" y="448" />
      <rect bind:this={strumTrigger} height="2112" width="64" x="678" y="448" />
    </g>
  </svg>
</main>

<audio bind:this={mySound} src='/strum.wav' />

<style>
  h1 {
    font-size: 3rem;
    text-align: center;
  }

  p, a {
    font-size: 1.5rem;
  }

  a {
    text-decoration: none;
    color: blueviolet;
  }

  section {
    width: 80vw;
    height: 40vh;
  }

  .hide {
    display: none;
  }

  .show {
    display: block;
  }

  .guitarSVG {
    transform: rotate(45deg);
    width: 80vw;
    height: 40vh;
  }

  @media only screen and (min-width: 900px){
    main {
      display: flex;
    }

    section {
      width: 50vw;
      height: 90vh;
    }

    .guitarSVG {
      width: 50vw;
      height: 70vh;
    }
  }
</style>