<template>
  <div class="component-wrapper d-flex justify-center py-5">
    <div class="wrapper d-flex flex-column">
      <!-- ====== DARK MODE BTN ====== -->
      <v-btn
        icon
        class="mb-5 align-self-end grey darken-4 white--text"
        @click="toggleDarkMode"
      >
        <v-icon>mdi-weather-night</v-icon>
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
          "
        >
          <div class="pa-5 text-center text-md-start">
            <div class="text-h6 font-weight-bold">Giannis Savvidis</div>
            <div class="body-1">Javascript Developer</div>
          </div>

          <div class="profile-inner-wrapper flex-md-column">
            <div class="img grey align-self-center align-self-md-stretch"></div>

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

                <div class="d-flex align-center mb-3">
                  <div class="body-2 font-weight-bold mr-2">Email:</div>
                  <div class="body-2">gsavvidis96@gmail.com</div>
                </div>

                <div class="d-flex align-center mb-3">
                  <div class="body-2 font-weight-bold mr-2">LinkedIn:</div>
                  <a
                    class="body-2 dotted"
                    href="https://www.linkedin.com/in/giannis-savvidis-22340a188/"
                    target="_blank"
                    >https://www.linkedin.com/in/giannis-savvidis-22340a188/</a
                  >
                </div>

                <div class="d-flex align-center mb-5">
                  <div class="body-2 font-weight-bold mr-2">Github:</div>
                  <a
                    class="body-2 dotted"
                    href="https://github.com/gsavvidis96"
                    target="_blank"
                    >https://github.com/gsavvidis96</a
                  >
                </div>

                <v-btn depressed>
                  <v-icon left>mdi-cloud-download-outline</v-icon>
                  Download CV</v-btn
                >
              </div>
            </div>
          </div>
        </div>

        <!-- ====== CV CARD ====== -->
        <div class="d-flex flex-column flex-grow-1">
          <div class="elevation-2 rounded mb-10 pa-5">
            <div class="text-h6 mb-5">About me</div>

            <div class="body-1 mb-10">
              Hi! I am Giannis, a web developer based in Athens, Greece. I love
              Javascript and always try to keep up with the fast-growing
              industry of web development, following the best practices and
              patterns. I look forward to working with you.
            </div>

            <div class="text-h6 mb-5">Education</div>

            <ul class="body-1 mb-10">
              <li class="mb-2">
                <a
                  href="https://michiganassessment.org/michigan-tests/ecpe-details/"
                  target="_blank"
                  >Certificate of Proficiency (ECPE)</a
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
              </li>
            </ul>

            <div class="text-h6 mb-5">Core Skills</div>

            <div class="mb-10">
              <v-chip
                v-for="skill in skills"
                :key="skill.name"
                class="ma-2"
                :color="skill.color"
                :class="{ 'white--text': skill.isWhite }"
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
                :class="{ 'white--text': technology.isWhite }"
                >{{ technology.name }}</v-chip
              >
            </div>

            <div class="text-h6 mb-5">Hobbies</div>

            <ul class="body-1">
              <li class="mb-2">Guitar</li>

              <li class="mb-2">Fitness</li>

              <li class="mb-2">Watching/Playing football (european)</li>
            </ul>
          </div>

          <!-- ====== FOOTER ====== -->
          <div
            class="
              grey
              darken-4
              rounded
              pa-3
              grey--text
              text--lighten-5
              footer
              d-flex
              flex-column
              align-center
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
          name: 'Strapi CMS',
          color: '#8e75ff',
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
        {
          name: 'Stripe payments',
          color: '#635bff',
          isWhite: true,
        },
        {
          name: 'Paypal',
          color: '#222d65',
          isWhite: true,
        },
      ],
    }
  },
  computed: {
    timeInCf() {
      const dateStarted = new Date(2019, 5, 1)
      const today = new Date()

      const years = today.getFullYear() - dateStarted.getFullYear()

      const months = today.getMonth() - dateStarted.getMonth()

      return `${years} Years${months ? ', ' + months + ' Months' : ''}`
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

.profile {
  .profile-inner-wrapper {
    display: flex;

    @media only screen and (max-width: 700px) {
      flex-direction: column;
    }
  }

  .img {
    height: 200px;

    @media only screen and (max-width: 960px) {
      height: 340px;
      width: 340px;
      border-bottom-left-radius: 4px;
      border-top-right-radius: 4px;
    }

    @media only screen and (max-width: 700px) {
      border-radius: 4px;
    }

    @media only screen and (max-width: 500px) {
      width: 100%;
      height: 300px;
    }
  }

  .dotted {
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    width: 180px;

    @media only screen and (max-width: 380px) {
      width: 150px;
    }
  }
}
</style>