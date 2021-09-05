<template>
  <div class="component-wrapper d-flex justify-center pb-10 pt-5">
    <div class="wrapper d-flex flex-column">
      <!-- ====== DARK MODE BTN ====== -->
      <v-btn
        icon
        class="mb-5 align-self-end grey darken-4 white--text"
        @click="toggleDarkMode"
      >
        <v-icon>mdi-weather-night</v-icon>
      </v-btn>

      <div class="d-flex">
        <!-- ====== INFO CARD ====== -->
        <div class="profile align-self-start elevation-2 rounded mr-10">
          <div class="pa-5">
            <div class="text-h6 font-weight-bold">Giannis Savvidis</div>
            <div class="body-1">Javascript Developer</div>
          </div>

          <div class="img grey"></div>

          <div class="pa-5">
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
              <div class="body-2">savvigiannhs@gmail.com</div>
            </div>

            <div class="d-flex align-center mb-3">
              <div class="body-2 font-weight-bold mr-2">Skype:</div>
              <div class="body-2">savvi_afanas</div>
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
                href="https://github.com/savgiannis"
                target="_blank"
                >https://github.com/savgiannis</a
              >
            </div>

            <v-btn depressed>
              <v-icon left>mdi-cloud-download-outline</v-icon>
              Download CV</v-btn
            >
          </div>
        </div>

        <!-- ====== CV CARD ====== -->
        <div class="d-flex flex-column flex-grow-1">
          <div class="elevation-2 rounded mb-10 pa-5">
            <div class="text-h6 mb-5">About me</div>

            <div class="body-1 mb-10">
              Lorem ipsum dolor, sit amet consectetur adipisicing elit. Alias,
              ipsum magni voluptas ducimus fuga eligendi nemo iusto deserunt
              accusamus. Provident hic sed repellat nam amet laborum sit culpa
              cupiditate, tempora velit mollitia quos, soluta illo error ad
              corporis? Totam id repellendus debitis odio blanditiis. Nisi, non.
              Officiis maxime incidunt delectus.
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
                <span class="body-2">(2 Years, 2 Months)</span>
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
          color: '#00dc82',
          isWhite: false,
        },
        {
          name: 'Strapi CMS',
          color: '#8e75ff',
          isWhite: true,
        },
        {
          name: 'Node.js',
          color: '#3c873a',
          isWhite: true,
        },
        {
          name: 'Express',
          color: '#aeaeae',
          isWhite: false,
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
          name: 'Firebase push notifications',
          color: '#ffca28',
          isWhite: false,
        },
        {
          name: 'Firebase hosting',
          color: '#ffca28',
          isWhite: false,
        },
        {
          name: 'Firebase cloud firestore',
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
      ],
    }
  },
  created() {
    console.log('xaxa', this.$vuetify.theme.dark)
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

  @media only screen and (max-width: 959px) {
    max-width: 900px;
  }

  @media only screen and (max-width: 599px) {
    width: 100%;
  }
}

.profile {
  .img {
    height: 200px;
  }

  .dotted {
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    width: 180px;
  }
}
</style>