<template>
  <section id="myrecentprojects" class="py-5 bg-light text-center">
    <div class="container py-5">

      <h1 class="mb-5" id="projects">SaaS & Web Application Projects</h1>

      <div class="row g-4">

        <!-- Card 5 -->
        <div class="col-12 col-md-6 col-lg-4">
          <div class="project-wrapper">
            <img src="/images/React-logo.png" class="project-img" />
            <div class="project-overlay d-flex flex-column justify-content-center align-items-center text-center px-3">
              <h3 class="text-white mb-2">Personal Trading Journal</h3>
              <a
                href="https://tradingjournal-one.vercel.app"
                target="_blank"
                class="btn btn-outline-light btn-sm rounded-pill px-3 mt-2"
              >
                View Project
              </a>
              <button
                class="btn btn-link text-white mt-2"
                @click="toggle(5)"
              >
                {{ open === 5 ? 'Hide details' : 'View details' }}
              </button>
            </div>
          </div>

          <transition name="collapse">
          <div v-if="open === 5" class="project-details mt-3 text-start">
            <p class="text-dark px-2 py-2">
            <strong>
              Built a full-stack personal trading journal to track trading performance, risk metrics, and equity growth, featuring secure authentication, performance dashboards, and a responsive UI. Deployed using Vercel (frontend) and Render (backend) with MongoDB integration.
            </strong>
          </p>

          <p class="text-dark px-2">
            <strong>Tech:</strong> React, Vite, Bootstrap, Node.js, Express, MongoDB, JWT, Chart.js, Render, Vercel
          </p>

          <ul class="project-list">
            <li>Designed and developed a full-stack trading journal to log trades, calculate performance metrics, and visualise equity growth</li>
            <li>Implemented secure user authentication using JWT with protected routes and token-based access control</li>
            <li>Built KPI dashboards displaying total trades, win rate, profit/loss, risk-reward ratios, and equity curve charts</li>
            <li>Integrated RESTful APIs for creating, updating, deleting, and analysing trade records</li>
            <li>Designed responsive, mobile-friendly UI components using Bootstrap and reusable React components</li>
            <li>Deployed the frontend on Vercel and backend on Render, managing environment variables and production builds</li>
            <li>Connected MongoDB for persistent trade storage and performance calculations</li>
          </ul>
          </div>
          </transition>
        </div>

        <!-- Card 4 -->
        <div class="col-12 col-md-6 col-lg-4">
          <div class="project-wrapper">
            <img src="/images/React-logo.png" class="project-img" />
            <div class="project-overlay d-flex flex-column justify-content-center align-items-center text-center px-3">
              <h3 class="text-white mb-2">Personal Job Application Tracker</h3>
              <a
                href="https://job-tracker-snowy-nine.vercel.app/login"
                target="_blank"
                class="btn btn-outline-light btn-sm rounded-pill px-3 mt-2"
              >
                View Project
              </a>
              <button
                class="btn btn-link text-white mt-2"
                @click="toggle(4)"
              >
                {{ open === 4 ? 'Hide details' : 'View details' }}
              </button>
            </div>
          </div>

          <transition name="collapse">
          <div v-if="open === 4" class="project-details mt-3 text-start">
            <p class="text-dark px-2 py-2"><strong>Built a full-stack job application tracker using React and Node.js, featuring authentication, status dashboards, and responsive UI. Deployed using Vercel and Render with MongoDB integration.</strong></p>
            <p class="text-dark px-2"><strong>Tech:</strong> React, Bootstrap, Node.js, Express, MongoDB, Render, Vercel</p>
            <ul class="project-list">
              <li>Designed and developed a full-stack job application tracking system for personal productivity</li>
              <li>Built responsive dashboards and data views to track application status (Applied, Interview, Offer, Rejected)</li>
              <li>Implemented secure authentication with JWT and protected routes</li>
              <li>Created reusable UI components (status cards, badges, dropdowns) for consistent user experience</li>
              <li>Integrated REST APIs for creating, updating, deleting, and displaying job applications</li>
            </ul>
          </div>
          </transition>
        </div>

        <!-- Card 3 -->
        <div class="col-12 col-md-6 col-lg-4">
          <div class="project-wrapper">
            <img src="/images/Caelas-logo.png" class="project-img" />
            <div class="project-overlay d-flex flex-column justify-content-center align-items-center text-center px-3">
              <h3 class="text-white mb-2">Caela's Treats</h3>
              <a
                href="https://caelas-treats.vercel.app/"
                target="_blank"
                class="btn btn-outline-light btn-sm rounded-pill px-3 mt-2"
              >
                View Project
              </a>
              <button
                class="btn btn-link text-white mt-2"
                @click="toggle(3)"
              >
                {{ open === 3 ? 'Hide details' : 'View details' }}
              </button>
            </div>
          </div>

          <transition name="collapse">
          <div v-if="open === 3" class="project-details mt-3 text-start">
            <p class="text-dark px-2 py-2"><strong>Full-stack e-commerce application with admin dashboard.</strong></p>
            <p class="text-dark px-2"><strong>Tech:</strong> Vue, Express, Node.js, MongoDB, Bootstrap, Vercel, AWS</p>
            <ul class="project-list">
              <li>Built product listings, search, and checkout flows</li>
              <li>Integrated payment processing</li>
              <li>Developed admin dashboard for orders and inventory</li>
              <li>Ensured responsive, mobile-first UX</li>
            </ul>
          </div>
          </transition>
        </div>
        
        <!-- Card 2 -->
        <div class="col-12 col-md-6 col-lg-4">
          <div class="project-wrapper">
            <img src="/images/Viaje-logo.png" class="project-img" />
            <div class="project-overlay d-flex flex-column justify-content-center align-items-center text-center px-3">
              <h3 class="text-white mb-2">Viaje Airlines</h3>
              <a
                href="https://viaje-client.vercel.app/"
                target="_blank"
                class="btn btn-outline-light btn-sm rounded-pill px-3 mt-2"
              >
                View Project
              </a>
              <button
                class="btn btn-link text-white mt-2"
                @click="toggle(2)"
              >
                {{ open === 2 ? 'Hide details' : 'View details' }}
              </button>
            </div>
          </div>

          <transition name="collapse">
          <div v-if="open === 2" class="project-details mt-3 text-start">
            <p class="text-dark px-2 py-2"><strong>SaaS-style booking interface concept focused on structured UI state and user flow.</strong></p>
            <p class="text-dark px-2"><strong>Tech:</strong> Vue, Express, Node.js, MongoDB, Bootstrap, Vercel, AWS</p>
            <ul class="project-list">
              <li>Implemented multi-step booking flow (search, select, confirm)</li>
              <li>Managed UI state and component structure</li>
              <li>Focused on reusable UI patterns</li>
              <li>Designed for clarity and responsiveness</li>
            </ul>
          </div>
          </transition>
        </div>



        <!-- Card 1 -->
        <div class="col-12 col-md-6 col-lg-4">
          <div class="project-wrapper">
            <img src="/images/CB-logo.png" class="project-img" />
            <div class="project-overlay d-flex flex-column justify-content-center align-items-center text-center px-3">
              <h3 class="text-white mb-2">Craft & Bauer Real Estate</h3>
              <a
                href="https://craftbauer.com/"
                target="_blank"
                class="btn btn-outline-light btn-sm rounded-pill px-3 mt-2"
              >
                View Project
              </a>
              <button
                class="btn btn-link text-white mt-2"
                @click="toggle(1)"
              >
                {{ open === 1 ? 'Hide details' : 'View details' }}
              </button>
            </div>
          </div>

          <!-- Collapsible Details -->
          
        <transition name="collapse">
          <div v-if="open === 1" class="project-details mt-3 text-start">
            <p class="text-dark px-2 py-2"><strong>Business website + CMS-driven marketing platform for a real estate firm.</strong></p>
            <p class="text-dark px-2"><strong>Tech:</strong> JavaScript, HTML, CSS, Bootstrap</p>
            <ul class="project-list">
              <li>Built responsive layouts optimised for property listings</li>
              <li>Improved UI consistency and mobile usability</li>
              <li>Implemented performance and cross-browser fixes</li>
              <li>Worked closely with business stakeholders on content updates</li>
            </ul>
          </div>
        </transition>
      </div>


      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      open: null
    }
  },
  methods: {
    toggle(id) {
      this.open = this.open === id ? null : id
    }
  }
}
</script>