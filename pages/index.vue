<template>
  <div class="component-wrapper d-flex justify-center py-5">
    <div class="wrapper d-flex flex-column">
      <!-- ====== DARK MODE BTN ====== -->
      <v-btn
        icon
        class="mb-5 align-self-end accent white--text"
        @click="toggleDarkMode"
      >
        <v-icon color="accentTextColor">{{
          isDarkMode ? 'mdi-white-balance-sunny' : 'mdi-weather-night'
        }}</v-icon>
      </v-btn>

      <div class="d-flex flex-column flex-md-row">
        <!-- ====== INFO CARD ====== -->
        <div
          class="
            profile
            align-self-md-start
            elevation-2
            rounded
            mb-10 mb-md-0
            mr-md-10
            background
          "
        >
          <div class="pa-5 text-center text-md-start">
            <div class="text-h5 mb-1 font-weight-bold">Giannis Savvidis</div>

            <div class="body-1">Software Developer</div>
          </div>

          <v-divider></v-divider>

          <div class="pa-5 d-flex justify-center justify-md-start">
            <div class="d-flex flex-column">
              <div class="d-flex align-center mb-3">
                <div class="body-2 font-weight-bold mr-2">Age:</div>
                <div class="body-2">{{ currentYear - 1996 }}</div>
              </div>

              <div class="d-flex align-center mb-3">
                <div class="body-2 font-weight-bold mr-2">Location:</div>
                <div class="body-2">Athens, Greece</div>
              </div>

              <div class="d-flex align-center mb-6">
                <div class="body-2 font-weight-bold mr-2">Email:</div>
                <div class="body-2">
                  <a href="mailto:someone@example.com">gsavvidis96@gmail.com</a>
                </div>
              </div>

              <v-btn
                depressed
                color="accent"
                class="accentTextColor--text mb-3"
                href="https://github.com/gsavvidis96"
                target="_blank"
              >
                <v-icon left> mdi-github</v-icon>
                Github</v-btn
              >

              <v-btn
                depressed
                color="accent"
                class="accentTextColor--text mb-3"
                href="https://www.linkedin.com/in/giannis-savvidis-22340a188/"
                target="_blank"
              >
                <v-icon left> mdi-linkedin</v-icon>
                LinkedIn</v-btn
              >

              <v-btn
                depressed
                color="accent"
                class="accentTextColor--text"
                href="GiannisSavvidisCV.pdf"
                download
              >
                <v-icon left>mdi-cloud-download-outline</v-icon>
                Download CV</v-btn
              >
            </div>
          </div>
        </div>

        <!-- ====== CV CARD ====== -->
        <div class="d-flex flex-column flex-grow-1">
          <div class="elevation-2 background rounded mb-10 pa-5">
            <div class="text-h6 mb-5">Summary</div>

            <div class="body-1">
              Software developer based in Athens, Greece. Always try to improve
              and keep up with the fast growing industry of software
              development, while following the best practices and writing clean
              and maintainable code.
            </div>

            <v-divider class="my-5"></v-divider>

            <div class="text-h6 mb-5">Core Skills</div>

            <div class="mb-8">
              <v-chip
                v-for="skill in skills"
                :key="skill.name"
                class="ma-2"
                outlined
                >{{ skill.name }}</v-chip
              >
            </div>

            <div class="text-h6 mb-5">Familiar With</div>

            <div>
              <v-chip
                v-for="technology in familiarWith"
                :key="technology.name"
                class="ma-2"
                outlined
                >{{ technology.name }}</v-chip
              >
            </div>

            <v-divider class="my-5"></v-divider>

            <div class="text-h6 mb-5">Professional Experience</div>

            <ul class="body-1">
              <li class="mb-2">
                <a href="https://codefactory.gr/" target="_blank">CodeFactory</a
                >, June 2019 - Present
                <span class="body-2">({{ timeInCf }})</span>
                <div class="body-1 pt-2">
                  Created web and mobile interfaces with Vue.js. Converted web
                  applications into mobile applications using Capacitor.js.
                  Created RESTful APIs with Node.js and Express.js. Involved in
                  the process of deploying to production servers and mobile
                  stores. Started many projects from scratch.
                </div>
              </li>
            </ul>

            <v-divider class="my-5"></v-divider>

            <div class="text-h6 mb-5">Education</div>

            <ul class="body-1">
              <li class="mb-2">
                <a href="http://www.ice.uniwa.gr/en/home/" target="_blank"
                  >Department of Informatics and Computer Engineering</a
                >,
                <span class="font-weight-medium"
                  >University of West Attica</span
                >
              </li>

              <li>
                <a
                  href="https://michiganassessment.org/michigan-tests/ecpe-details/"
                  target="_blank"
                  >Certificate of Proficiency in English (ECPE)</a
                >,
                <span class="font-weight-medium">University of Michigan</span>
              </li>
            </ul>

            <v-divider class="my-5"></v-divider>

            <div class="text-h6 mb-5">Hobbies</div>

            <ul class="body-1">
              <li class="mb-2">Guitar</li>

              <li class="mb-2">Fitness</li>
            </ul>
          </div>

          <!-- ====== FOOTER ====== -->
          <div
            class="
              rounded
              pa-3
              footer
              d-flex
              flex-column
              align-center
              accent
              accentTextColor--text
            "
          >
            <div class="caption">Giannis Savvidis &copy; {{ currentYear }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
      skills: [
        {
          name: 'JavaScript',
          color: '#f7df1e',
          isWhite: false,
        },
        {
          name: 'TypeScript',
          color: '#007acc',
          isWhite: true,
        },
        {
          name: 'CSS / SCSS',
          color: '#2965f1',
          isWhite: true,
        },
        {
          name: 'Vue.js (2 & 3)',
          color: '#42b883',
          isWhite: true,
        },
        {
          name: 'Capacitor.js',
          color: '#119eff',
          isWhite: true,
        },
        {
          name: 'Node.js',
          color: '#3c873a',
          isWhite: true,
        },
        {
          name: 'Express.js',
          color: '#aeaeae',
          isWhite: true,
        },
        {
          name: 'Nest.js',
          color: '#ed1543',
          isWhite: true,
        },
        {
          name: 'PostgreSQL',
          color: '#336791',
          isWhite: true,
        },
        {
          name: 'Redis',
          color: '#d82c20 ',
          isWhite: true,
        },
        {
          name: 'Docker',
          color: '#0db7ed ',
          isWhite: true,
        },
        {
          name: 'Jest',
          color: '#e49c84 ',
          isWhite: true,
        },
      ],
      familiarWith: [
        {
          name: 'React.js',
          color: '#61dafb',
          isWhite: false,
        },
        {
          name: 'MongoDB',
          color: '#13aa52',
          isWhite: true,
        },
        {
          name: 'Kubernetes',
          color: '#3371e3',
          isWhite: true,
        },
        {
          name: 'Microservices',
          color: '#aeaeae',
          isWhite: true,
        },
        {
          name: 'CI / CD',
          color: '#aeaeae',
          isWhite: true,
        },
      ],
    }
  },
  computed: {
    timeInCf() {
      const dateStarted = this.$dayjs(new Date(2019, 5, 1))

      const today = this.$dayjs()

      const diff = today.diff(dateStarted, 'months')

      const years = Math.trunc(diff / 12)

      const months = diff % 12

      return `${years} Years${months ? ', ' + months + ' Months' : ''}`
    },
    isDarkMode() {
      return this.$vuetify.theme.dark
    },
  },
  beforeMount() {
    if (!localStorage.getItem('isDarkMode')) {
      // if not exists
      if (
        window.matchMedia &&
        window.matchMedia('(prefers-color-scheme: dark)').matches
      ) {
        localStorage.setItem('isDarkMode', 'yes')
      } else {
        localStorage.setItem('isDarkMode', 'no')
      }
    }

    const isDarkMode = localStorage.getItem('isDarkMode') // get last saved dark mode

    setTimeout(() => {
      this.$vuetify.theme.dark = isDarkMode === 'yes'
    }, 1)
  },
  methods: {
    toggleDarkMode() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark

      localStorage.setItem(
        'isDarkMode',
        this.$vuetify.theme.dark ? 'yes' : 'no'
      )
    },
  },
}
</script>

<style lang="scss" scoped>
.wrapper {
  max-width: 1185px;

  @media only screen and (max-width: 1225px) {
    max-width: 900px;
  }

  @media only screen and (max-width: 960px) {
    width: 100%;
    padding: 0 20px;
  }
}
</style>
