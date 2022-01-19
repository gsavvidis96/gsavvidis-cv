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

            <div class="body-1">Web Developer</div>
          </div>

          <v-divider></v-divider>

          <div class="pa-5 d-flex justify-center justify-md-start">
            <div class="d-flex flex-column">
              <div class="d-flex align-center mb-3">
                <div class="body-2 font-weight-bold mr-2">Age:</div>
                <div class="body-2">{{ currentYear - 1996 }}</div>
              </div>

              <div class="d-flex align-center mb-3">
                <div class="body-2 font-weight-bold mr-2">Residence:</div>
                <div class="body-2">Athens, Greece</div>
              </div>

              <div class="d-flex align-center mb-3">
                <div class="body-2 font-weight-bold mr-2">Nationality:</div>
                <div class="body-2">Greek</div>
              </div>

              <div class="d-flex align-center mb-3">
                <div class="body-2 font-weight-bold mr-2">Mobile:</div>
                <div class="body-2">+30 6977456192</div>
              </div>

              <div class="d-flex align-center mb-6">
                <div class="body-2 font-weight-bold mr-2">Email:</div>
                <div class="body-2">gsavvidis96@gmail.com</div>
              </div>

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
                href="https://firebasestorage.googleapis.com/v0/b/gsavvidis-d189f.appspot.com/o/cv.pdf?alt=media"
                target="_blank"
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
            <div class="text-h6 mb-5">About me</div>

            <div class="body-1 mb-10">
              I am Giannis, a web developer based in Athens, Greece. I love
              JavaScript and always try to keep up with the fast-growing
              industry of web development, following the best practices and
              patterns.
            </div>

            <div class="text-h6 mb-5">Education</div>

            <ul class="body-1 mb-10">
              <li class="mb-2">
                <a
                  href="https://michiganassessment.org/michigan-tests/ecpe-details/"
                  target="_blank"
                  >Certificate of Proficiency in English (ECPE)</a
                >,
                <span class="font-weight-medium">University of Michigan</span>
              </li>

              <li>
                <a href="http://www.ice.uniwa.gr/en/home/" target="_blank"
                  >Department of Informatics and Computer Engineering</a
                >,
                <span class="font-weight-medium"
                  >University of West Attica</span
                >
                (Undergraduate)
              </li>
            </ul>

            <div class="text-h6 mb-5">Employment</div>

            <ul class="body-1 mb-10">
              <li class="mb-2">
                <a href="https://codefactory.gr/" target="_blank">CodeFactory</a
                >, June 2019 - Present
                <span class="body-2">({{ timeInCf }})</span>
                <div class="body-1 pt-2">
                  As a front-end developer I was creating interfaces with Vue.js
                  following the best practices. Used modern features like push
                  notifications, WebRTC and more. Converted web applications
                  into hybrid mobile applications using Capacitor.js and
                  published to both Google Play Store and Apple App Store. I
                  consumed a variety of RESTful APIs as well as implemented some
                  with Node.js and Express.js.
                </div>
              </li>
            </ul>

            <div class="text-h6 mb-5">Core Skills</div>

            <div class="mb-10">
              <v-chip
                v-for="skill in skills"
                :key="skill.name"
                class="ma-2"
                :color="skill.color"
                :class="{
                  'white--text': skill.isWhite,
                  'black--text': !skill.isWhite,
                }"
                >{{ skill.name }}</v-chip
              >
            </div>

            <div class="text-h6 mb-5">Other Major Technologies</div>

            <div class="mb-10">
              <v-chip
                v-for="technology in technologies"
                :key="technology.name"
                class="ma-2"
                :color="technology.color"
                :class="{
                  'white--text': technology.isWhite,
                  'black--text': !technology.isWhite,
                }"
                >{{ technology.name }}</v-chip
              >
            </div>

            <div class="text-h6 mb-5">Hobbies</div>

            <ul class="body-1">
              <li class="mb-2">Guitar</li>

              <li class="mb-2">Fitness</li>

              <li class="mb-2">Watching/playing football</li>
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
          name: 'Javascript',
          color: '#f7df1e',
          isWhite: false,
        },
        {
          name: 'Vue',
          color: '#42b883',
          isWhite: true,
        },
        {
          name: 'CSS',
          color: '#2965f1',
          isWhite: true,
        },
        {
          name: 'Nuxt',
          color: '#00c58e',
          isWhite: true,
        },
        {
          name: 'Node',
          color: '#3c873a',
          isWhite: true,
        },
        {
          name: 'Express',
          color: '#aeaeae',
          isWhite: true,
        },
        {
          name: 'MySQL',
          color: '#f29111',
          isWhite: true,
        },
      ],
      technologies: [
        {
          name: 'Vuetify',
          color: '#1697f6',
          isWhite: true,
        },
        {
          name: 'Capacitor.js',
          color: '#119eff',
          isWhite: true,
        },
        {
          name: 'PWA',
          color: '#5a0fc8',
          isWhite: true,
        },
        {
          name: 'Sequelize ORM',
          color: '#237bbb',
          isWhite: true,
        },
        {
          name: 'Prisma ORM',
          color: '#48bb78',
          isWhite: true,
        },
        {
          name: 'Firebase',
          color: '#ffca28',
          isWhite: false,
        },
        {
          name: 'Twilio video',
          color: '#f22f46',
          isWhite: true,
        },
        // {
        //   name: 'Stripe payments',
        //   color: '#635bff',
        //   isWhite: true,
        // },
        // {
        //   name: 'Paypal',
        //   color: '#222d65',
        //   isWhite: true,
        // },
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
  methods: {
    toggleDarkMode() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
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
