<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  
  // Icons
  const ArrowRight = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>`;
  const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
  const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
  const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
  const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>`;
  const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
  const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
  const LinkedIn = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
  const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 12"/></svg>`;

  // Data
  const heroImages = [
    "/generated/image-australian-primary-school-students-at-a--1765580623212-0.webp", // Swimming carnival
    "/generated/image-australian-high-school-students-competin-1765580626604-1.webp", // Athletics track
    "/generated/image-australian-school-students-playing-crick-1765580629413-2.webp", // Cricket
    "/generated/image-australian-school-netball-team-celebrati-1765580632166-3.webp", // Netball
    "/generated/image-australian-school-cross-country-running--1765580634715-4.webp", // Cross-country
    "/generated/image-australian-school-athletics-carnival-div-1765580637360-5.webp"  // Long jump
  ];

  const benefitCards = [
    {
      title: "Celebrate every achievement.",
      desc: "From participation to championship glory, recognize students with badges, trophies, and awards that build their personal athlete portfolio.",
      image: "/generated/image-young-australian-students-celebrating-wi-1765580639961-6.webp"
    },
    {
      title: "Real-time competition management.",
      desc: "Auto-generate fixtures, track live results, calculate ladders automatically. Set up your carnival in 5 minutes, not 5 hours.",
      image: "/generated/image-australian-pe-teacher-or-sports-coordina-1765580642396-7.webp"
    },
    {
      title: "Keep everyone connected.",
      desc: "Instant notifications for coaches, students, and parents. Over 1 million notifications delivered and 500,000+ messages sent.",
      image: "/generated/image-australian-school-students-checking-resu-1765580645008-8.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Choose your carnival template.",
      desc: "Select from pre-built templates for swimming carnivals, athletics meets, house competitions, or create your own custom format. Set up in 5 minutes.",
      image: "plan"
    },
    {
      step: 2,
      title: "Add teams and athletes.",
      desc: "Import your student lists, create house teams, and assign athletes to events. Bulk upload or add individually—whatever works for your school.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Auto-generate fixtures.",
      desc: "Let Sports Meister automatically create your competition schedule, heats, and groups. Customize as needed with our intuitive drag-and-drop interface.",
      image: "results"
    },
    {
      step: 4,
      title: "Track results in real-time.",
      desc: "Enter scores and times as events happen. Ladders update automatically, students see their results instantly, and parents get live notifications.",
      image: "notes"
    },
    {
      step: 5,
      title: "Award achievements and celebrate.",
      desc: "Students earn badges, build their trophy cabinet, and create a personal athlete portfolio. Track their journey from first game to championship glory.",
      image: "improve"
    }
  ];

  const faqs = [
    "How quickly can we set up our first carnival?",
    "What sports and competition formats are supported?",
    "Can parents and students access the platform?",
    "Is our school data secure and private?",
    "What happens to student achievement data when they graduate?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Unified athlete achievement<br />tracking for Australian schools.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      Real-time competition management and gamified recognition system. Trusted by 200+ Australian schools managing 75,000+ matches. Set up in 5 minutes.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Start Free Trial
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Australian school sports" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- App Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Phone Mockup -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-[280px] h-[580px] bg-black rounded-[40px] border-[8px] border-black shadow-2xl overflow-hidden">
          <div class="absolute top-0 left-0 right-0 h-6 bg-black z-20 flex justify-center">
            <div class="w-20 h-4 bg-black rounded-b-xl"></div>
          </div>
          <div class="w-full h-full bg-white pt-10 px-4 overflow-hidden flex flex-col">
            <!-- Mock UI -->
            <div class="flex justify-between items-center mb-6">
              <div class="w-8 h-8 rounded-full bg-primary-200 flex items-center justify-center text-xs font-bold">SM</div>
              <div class="w-8 h-8 rounded-full bg-gray-100 flex items-center justify-center">
                <div class="w-1 h-1 bg-gray-400 rounded-full"></div>
              </div>
            </div>
            <div class="mb-6">
              <div class="text-xs text-gray-500 mb-1">Athletics Carnival</div>
              <div class="text-xl font-bold">Live Results</div>
            </div>
            <div class="space-y-3">
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="flex justify-between items-center mb-2">
                  <div class="text-[10px] font-medium">100m Sprint - Heat 1</div>
                  <div class="text-[8px] text-green-600 font-medium">LIVE</div>
                </div>
                <div class="w-full h-1.5 bg-green-400 rounded"></div>
              </div>
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="flex justify-between items-center mb-2">
                  <div class="text-[10px] font-medium">Long Jump - Finals</div>
                  <div class="text-[8px] text-gray-400">Starting soon</div>
                </div>
                <div class="w-2/3 h-1.5 bg-primary-400 rounded"></div>
              </div>
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="flex justify-between items-center mb-2">
                  <div class="text-[10px] font-medium">Relay 4x100m</div>
                  <div class="text-[8px] text-gray-400">Scheduled</div>
                </div>
                <div class="w-1/3 h-1.5 bg-gray-300 rounded"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-8">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Every achievement tracked.<br />
          Live competition results, automatic ladder calculations, and gamified badges. Students, coaches, and parents stay connected with real-time notifications and a complete athlete portfolio.
        </h2>
        <div class="flex items-center justify-between pt-4">
          <button class="flex items-center gap-2 text-[#1A1A1A] font-medium hover:opacity-70 transition-opacity">
            {@html PlayCircle}
            Watch demo
          </button>
          <div class="flex gap-2">
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronLeft}
            </button>
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronRight}
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto" id="features">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-medium tracking-tight text-[#1A1A1A] leading-tight">
        Every student deserves recognition for their achievements.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        From their first carnival to championship glory, Sports Meister tracks every milestone. We help schools celebrate participation, effort, and excellence—building confidence and creating memories that last a lifetime. Because every achievement matters.
      </p>
    </div>
  </section>

  <!-- Benefit Cards -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-3 gap-6">
      {#each benefitCards as card}
        <div class="relative h-[480px] rounded-3xl overflow-hidden group">
          <img src={card.image} alt={card.title} class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/20 to-transparent"></div>
          <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
            <h3 class="text-2xl font-medium mb-3">{card.title}</h3>
            <p class="text-white/80 text-sm leading-relaxed font-light">{card.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Testimonial -->
  <section class="py-24 px-6 max-w-4xl mx-auto text-center">
    <blockquote class="text-2xl md:text-3xl font-medium leading-relaxed text-[#1A1A1A] mb-8">
      "Sports Meister has transformed how we run our school carnivals. What used to take me hours of spreadsheet work now happens in minutes. The kids love seeing their achievements build up, and parents actually know what's happening in real-time. It's a game-changer."
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="/generated/image-australian-school-sports-coordinator-pro-1765580647464-9.webp" alt="Sports Coordinator" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Sarah Mitchell</div>
        <div class="text-gray-500 text-xs">Sports Coordinator, Melbourne Grammar</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">200+ Australian schools.</h3>
        <p class="text-gray-500 text-sm font-light">Trusted by primary and secondary schools across Australia for their sports carnivals and competitions.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">50,000+ active athletes.</h3>
        <p class="text-gray-500 text-sm font-light">Students building their personal athlete portfolios from first game to championship glory.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">75,000+ matches managed.</h3>
        <p class="text-gray-500 text-sm font-light">Real-time results, automatic ladders, and 25,000+ achievement awards earned by students.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">From carnival setup to championship celebrations, Sports Meister handles the admin so you can focus on what matters—supporting your students. Set up in 5 minutes, manage in real-time, celebrate forever.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-white rounded-[40px] p-8 md:p-12 flex flex-col items-center text-center max-w-2xl mx-auto shadow-sm">
          <div class="w-full text-left mb-8">
            <span class="inline-block w-8 h-8 rounded-full border border-gray-200 text-center leading-8 text-sm font-medium mb-4">{step.step}</span>
            <h3 class="text-2xl font-medium mb-3">{step.title}</h3>
            <p class="text-gray-500 font-light text-sm max-w-lg">{step.desc}</p>
          </div>
          
          <!-- Phone Mockup for Step -->
          <div class="relative w-[240px] h-[480px] bg-black rounded-[35px] border-[6px] border-black shadow-xl overflow-hidden mt-4">
             <div class="absolute top-0 left-0 right-0 h-5 bg-black z-20 flex justify-center">
                <div class="w-16 h-3 bg-black rounded-b-lg"></div>
             </div>
             <div class="w-full h-full bg-white pt-8 px-3 overflow-hidden">
                <!-- Dynamic Content based on step -->
                {#if step.image === 'plan'}
                  <div class="space-y-3 mt-4">
                    <div class="p-3 border-2 rounded-xl border-primary-500 bg-primary-50">
                      <div class="font-bold text-xs mb-1">🏊 Swimming Carnival</div>
                      <div class="text-[8px] text-gray-500">Pre-built template</div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-600">🏃 Athletics Meet</div>
                       <div class="text-[8px] text-gray-400">Pre-built template</div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-600">🏏 House Cricket</div>
                       <div class="text-[8px] text-gray-400">Pre-built template</div>
                    </div>
                  </div>
                {:else if step.image === 'schedule'}
                   <div class="mt-4">
                     <div class="text-center font-bold text-sm mb-4">Add Athletes</div>
                     <div class="space-y-2 mb-3">
                       <div class="bg-gray-100 p-2 rounded-lg flex items-center gap-2">
                         <div class="w-6 h-6 rounded-full bg-red-400"></div>
                         <div class="text-[10px] font-medium">Red House - 24 athletes</div>
                       </div>
                       <div class="bg-gray-100 p-2 rounded-lg flex items-center gap-2">
                         <div class="w-6 h-6 rounded-full bg-blue-400"></div>
                         <div class="text-[10px] font-medium">Blue House - 22 athletes</div>
                       </div>
                       <div class="bg-gray-100 p-2 rounded-lg flex items-center gap-2">
                         <div class="w-6 h-6 rounded-full bg-green-400"></div>
                         <div class="text-[10px] font-medium">Green House - 26 athletes</div>
                       </div>
                     </div>
                     <button class="w-full bg-black text-white text-xs py-2 rounded-lg">Import from CSV</button>
                   </div>
                {:else if step.image === 'results'}
                   <div class="bg-white h-full -mx-3 -mt-8 pt-10 px-3">
                      <div class="text-center mb-4">
                        <div class="text-xs font-bold mb-2">Auto-Generated Fixtures</div>
                      </div>
                      <div class="space-y-2">
                         <div class="bg-gray-100 p-2 rounded-lg">
                           <div class="text-[9px] font-medium mb-1">Heat 1 - 9:00 AM</div>
                           <div class="text-[8px] text-gray-500">Lanes 1-6 assigned</div>
                         </div>
                         <div class="bg-gray-100 p-2 rounded-lg">
                           <div class="text-[9px] font-medium mb-1">Heat 2 - 9:15 AM</div>
                           <div class="text-[8px] text-gray-500">Lanes 1-6 assigned</div>
                         </div>
                         <div class="bg-gray-100 p-2 rounded-lg">
                           <div class="text-[9px] font-medium mb-1">Heat 3 - 9:30 AM</div>
                           <div class="text-[8px] text-gray-500">Lanes 1-6 assigned</div>
                         </div>
                      </div>
                      <button class="w-full bg-primary-500 text-white text-xs py-2 rounded-lg mt-3">Customize Schedule</button>
                   </div>
                {:else if step.image === 'notes'}
                   <div class="mt-4 space-y-3">
                      <div class="font-bold text-sm">Live Results</div>
                      <div class="bg-green-50 border border-green-200 p-2 rounded-lg">
                        <div class="flex justify-between items-center mb-1">
                          <div class="text-[10px] font-bold">🥇 1st Place</div>
                          <div class="text-[9px] text-green-700">12.4s</div>
                        </div>
                        <div class="text-[9px] text-gray-600">Emma Wilson - Red House</div>
                      </div>
                      <div class="bg-gray-50 border border-gray-200 p-2 rounded-lg">
                        <div class="flex justify-between items-center mb-1">
                          <div class="text-[10px] font-bold">🥈 2nd Place</div>
                          <div class="text-[9px] text-gray-600">12.6s</div>
                        </div>
                        <div class="text-[9px] text-gray-600">Jake Chen - Blue House</div>
                      </div>
                      <div class="text-[8px] text-green-600 text-center mt-2">✓ Parents notified</div>
                   </div>
                {:else}
                   <div class="mt-4 flex flex-col h-full">
                      <div class="flex-1 space-y-3">
                        <div class="text-center mb-3">
                          <div class="text-xs font-bold">Achievement Unlocked!</div>
                        </div>
                        <div class="bg-primary-50 border-2 border-primary-300 p-3 rounded-xl text-center">
                          <div class="text-2xl mb-1">🏆</div>
                          <div class="text-[10px] font-bold">Sprint Champion</div>
                          <div class="text-[8px] text-gray-500">Won 3 races</div>
                        </div>
                        <div class="bg-gray-50 p-2 rounded-lg">
                          <div class="text-[9px] font-medium mb-1">Trophy Cabinet</div>
                          <div class="flex gap-1 justify-center">
                            <div class="text-lg">🥇</div>
                            <div class="text-lg">🏅</div>
                            <div class="text-lg">⭐</div>
                          </div>
                        </div>
                      </div>
                   </div>
                {/if}
             </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Dark Cards Section -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Reliability Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Built for Australian schools.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">SSL secure, GDPR compliant, and WCAG 2.1 AA accessible.</h2>
        </div>
        <!-- Abstract Shield Visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-20 mt-20">
           <svg viewBox="0 0 200 200" class="w-64 h-64 text-gray-500 stroke-current fill-none">
              <path d="M100 20 L160 50 L160 100 Q160 140 100 180 Q40 140 40 100 L40 50 Z" stroke-width="2"/>
              <path d="M70 100 L90 120 L130 70" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
           </svg>
        </div>
      </div>

      <!-- Privacy Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Student data protection.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Privacy-first design for K-12 student information.</h2>
        </div>
        <!-- Blurred Text Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden">
           <div class="text-4xl font-mono text-gray-600 opacity-20 blur-sm select-none break-all p-8">
             Stud3nt|%D@ta Sch00l|R3c0rds Ach!ev3|Pr!vacy
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="pricing">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Simple pricing for Australian schools.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">Start with a free trial. No credit card required. Set up your first carnival in 5 minutes and see why 200+ schools trust Sports Meister.</p>
    </div>

    <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
      <!-- Free Trial -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col">
        <div class="w-12 h-12 bg-gray-100 rounded-full mb-6 flex items-center justify-center">
          <span class="text-2xl">🎯</span>
        </div>
        <h3 class="text-2xl font-medium mb-1">Free Trial</h3>
        <p class="text-sm text-gray-500 mb-6">Try Sports Meister risk-free.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">$0</span>
          <span class="text-gray-400 text-sm">/30 days</span>
          <div class="text-[10px] text-primary-600 mt-1 font-medium">No credit card required.</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Full access to all features for 30 days.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Pre-built carnival templates for quick setup.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Up to 100 athletes and unlimited events.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Start Free Trial</button>
      </div>

      <!-- School Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col relative overflow-hidden">
        <div class="absolute top-0 right-0 bg-[#FFF8E1] px-4 py-1 rounded-bl-xl text-xs font-medium text-orange-800">Most Popular</div>
        <div class="w-12 h-12 bg-primary-100 rounded-full mb-6 flex items-center justify-center">
          <span class="text-2xl">🏆</span>
        </div>
        <h3 class="text-2xl font-medium mb-1">School Plan</h3>
        <p class="text-sm text-gray-500 mb-6">For growing school sports programs.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">Contact us</span>
          <div class="text-[10px] text-primary-600 mt-1 font-medium">Custom pricing for your school.</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Unlimited athletes, events, and competitions.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Multi-year athlete portfolio tracking.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Priority support and onboarding assistance.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Contact Sales</button>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Frequently asked questions.</h2>
    <div class="space-y-4">
      {#each faqs as question}
        <div class="border-b border-gray-200 py-4 flex justify-between items-center cursor-pointer group hover:bg-gray-50/50 transition-colors px-2">
          <span class="text-sm md:text-base font-medium text-gray-800">{question}</span>
          <span class="text-gray-400 group-hover:text-black transition-colors">{@html Plus}</span>
        </div>
      {/each}
    </div>
    <div class="mt-12 text-center">
      <button class="border border-gray-300 px-6 py-3 rounded-sm text-xs font-medium hover:bg-gray-50 transition-colors">
        View All FAQs
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
           <div class="w-7 h-7 text-[#1A1A1A]">
             <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
               <path
                 fill-rule="evenodd"
                 clip-rule="evenodd"
                 d="M5.0473 17.8386L5.69453 18.9586V18.9601H18.3003L18.9314 17.84H6.34063L6.82626 16.9993H19.4308L20.078 15.8807H7.47237L7.95715 15.0414H16.0358L16.0366 15.0429L16.0375 15.0414H20.5603L20.5612 15.0429L21.2084 13.9228L21.208 13.922L21.2084 13.9213H21.2075L14.9084 3.00677L14.9106 3.00296L14.9062 3.00296L13.6177 3.00296L5.0473 17.8386ZM14.261 4.12767L13.7751 4.96887L18.9438 13.9213H19.9139L14.261 4.12767ZM13.1286 6.08808L12.6467 6.9225L16.6749 13.9006L16.6634 13.9213H17.6511L13.1286 6.08808ZM11.9999 8.04225L8.60411 13.9213H15.3899L11.9999 8.04225ZM6.99833 3.30006C7.33866 3.10343 7.7248 2.99993 8.11786 3L2.30033 13.0776C2.10357 12.7371 2 12.3508 2 11.9575C2 11.5643 2.10357 11.178 2.30033 10.8375L6.17916 4.12006C6.37543 3.77951 6.65798 3.49669 6.99833 3.30006ZM9.08869 3H10.3816L3.43223 15.0384L2.785 13.9184L9.08869 3ZM11.3509 3H12.6424L4.56262 16.9963L3.91691 15.8777L11.3509 3ZM21.7064 13.0598C21.8988 12.7254 22 12.3463 22 11.9605C22 11.5746 21.8988 11.1956 21.7064 10.8611L17.8039 4.10233C17.6108 3.7681 17.3331 3.49057 16.9987 3.2976C16.6644 3.10463 16.2852 3.00302 15.8992 3.00296H15.8741L21.6931 13.082L21.7064 13.0598ZM17.7995 19.7994H6.17916C6.37472 20.1412 6.65692 20.4253 6.99728 20.6232C7.33763 20.8212 7.72414 20.9258 8.11786 20.9269H15.8829C16.2737 20.9261 16.6572 20.8212 16.994 20.6231C17.3309 20.4249 17.6089 20.1406 17.7995 19.7994Z"
                 fill="currentColor"
               />
             </svg>
           </div>
           <span class="font-bold text-lg tracking-tight">Sports Meister</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#features" class="hover:text-black">Features</a>
          <a href="#faq" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Blog</a>
          <a href="#" class="hover:text-black">Terms & Conditions</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="#" class="hover:text-black">{@html XIcon}</a>
          <a href="#" class="hover:text-black">{@html Instagram}</a>
          <a href="#" class="hover:text-black">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-4 text-sm font-medium text-gray-600">Made with ❤️ in Australia for Australian Schools</p>
        <p class="mb-2">Sports Meister is a sports management technology platform designed specifically for Australian K-12 schools. All student data is stored securely and handled in accordance with Australian privacy laws and educational data protection requirements. Schools maintain full ownership and control of their data. Sports Meister provides technology services only and does not provide educational advice or replace school administrative procedures.</p>
        <p class="mb-2">Pricing is based on school size and usage requirements. Free trial includes full feature access for 30 days with no credit card required. For custom pricing and enterprise features, contact our sales team. All prices are in Australian dollars unless otherwise stated.</p>
        <p class="mt-2">By using Sports Meister, schools agree to our Terms of Service and Privacy Policy. For questions about data handling, security, or compliance, please contact our support team.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  :global(body) {
    background-color: #F9F8F6;
    font-family: 'Inter', sans-serif;
  }
  
  .hide-scrollbar::-webkit-scrollbar {
    display: none;
  }
  .hide-scrollbar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>

