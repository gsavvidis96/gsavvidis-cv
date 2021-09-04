<template>
  <v-container class="pt-12 d-flex">
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

    <div class="d-flex flex-column flex-grow-1">
      <div class="elevation-2 rounded mb-10 pa-5">
        <div class="text-h6 mb-5">About me</div>

        <div class="body-1 mb-10">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Alias, ipsum
          magni voluptas ducimus fuga eligendi nemo iusto deserunt accusamus.
          Provident hic sed repellat nam amet laborum sit culpa cupiditate,
          tempora velit mollitia quos, soluta illo error ad corporis? Totam id
          repellendus debitis odio blanditiis. Nisi, non. Officiis maxime
          incidunt delectus.
        </div>

        <div class="text-h6 mb-5">Education</div>

        <ul class="body-1 mb-10">
          <li class="mb-2">
            <a
              href="https://michiganassessment.org/michigan-tests/ecpe/"
              target="_blank"
              >Certificate of Proficiency (ECPE)</a
            >,
            <span class="font-weight-medium">University of Michigan</span>
          </li>

          <li>
            <a href="http://www.ice.uniwa.gr/en/home/" target="_blank"
              >Department of Informatics and Computer Engineering</a
            >,
            <span class="font-weight-medium">University of West Attica</span>
            (Undergraduate)
          </li>
        </ul>

        <div class="text-h6 mb-5">Employment</div>

        <ul class="body-1 mb-10">
          <li class="mb-2">
            <a href="https://codefactory.gr/" target="_blank">CodeFactory</a>,
            June 2019 - Present
            <span class="body-2">(2 Years, 2 Months)</span>
          </li>
        </ul>

        <div class="text-h6 mb-5">Skills</div>

        <div class="mb-10">
          <v-chip class="ma-2" color="#f7df1e">Javascript</v-chip>

          <v-chip class="ma-2 white--text" color="#42b883">Vue</v-chip>

          <v-chip class="ma-2 white--text" color="#1697f6">Vuetify</v-chip>

          <v-chip class="ma-2 white--text" color="#2965f1">CSS</v-chip>

          <v-chip class="ma-2" color="#00dc82">Nuxt</v-chip>

          <v-chip class="ma-2 white--text" color="#119eff">Capacitor.js</v-chip>

          <v-chip class="ma-2 white--text" color="#8e75ff">Strapi CMS</v-chip>

          <v-chip class="ma-2 white--text" color="#3c873a">Node.js</v-chip>

          <v-chip class="ma-2" color="#aeaeae">Express</v-chip>

          <v-chip class="ma-2 white--text" color="#f29111">MySQL</v-chip>

          <v-chip class="ma-2 white--text" color="#237bbb"
            >Sequelize ORM</v-chip
          >

          <v-chip class="ma-2 white--text" color="#48bb78">Prisma ORM</v-chip>

          <v-chip class="ma-2" color="#FFCA28">Firebase</v-chip>
        </div>

        <div class="text-h6 mb-5">Hobbies</div>

        <ul class="body-1">
          <li class="mb-2">Guitar</li>

          <li class="mb-2">Fitness</li>

          <li class="mb-2">Watching/Playing football (european)</li>
        </ul>
      </div>

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
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
    }
  },
}
</script>

<style lang="scss" scoped>
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