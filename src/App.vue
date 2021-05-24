<template>
  <transition name="fade" tag="div" class="wrapper" mode="out-in">
    <div class="wrapper" v-if="isLoaded" id="app">
      <LandingPage :user="user" />
      <Description
        :user="user"
        :content="findSlug('description')"
        :links="findSlug('links')"
      />
      <Experience :content="findSlug('experiences')" />
      <Skills :content="findSlug('skills')" />
      <Projects :content="findSlug('projects')" />
      <Footer :user="user" :links="findSlug('links')" />
    </div>
  </transition>
</template>

<script>
import LandingPage from "./components/LandingPage.vue";
import Description from "./components/Description.vue";
import Experience from "./components/Experience.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    LandingPage,
    Description,
    Experience,
    Skills,
    Projects,
    Footer
  },
  data() {
    return {
      isLoaded: false,
      user: {
        name: "William Urbina",
        status: "Full Stack Developer",
        email: "williamjkc69@gmail.com",
        phone: "+503 6116 8813",
        city: "Cuscatlán, El Salvador",
        lang: "Spanish, English",
        photo: "my-photo.png"
      },
      posts: [
        {
          slug: "projects",
          title: "projects",
          metadata: {
            items: [
              {
                title: "react store",
                content:
                  "Package to create dynamic tables in Vue <br><br>Link : <a href='https://github.com/williamjkc69/react-store'>https://github.com/williamjkc69/react-store</a>",
                link: "https://github.com/williamjkc69/react-store",
                // image: "ig.gif",
                tag: "webpage",
                color: "purple",
                date: "2020-04-01"
              },
              {
                title: "v-datatable",
                content:
                  "Package to create dynamic tables in Vue <br><br>Link : <a href='https://github.com/williamjkc69/v-datatable'>https://github.com/williamjkc69/v-datatable</a>",
                link: "https://github.com/williamjkc69/v-datatable",
                // image: "ig.gif",
                tag: "library",
                color: "green",
                date: "2020-01-01"
              },
              {
                title: "TODO ionic-firebase",
                content:
                  "App created with Ionic and Firebase, include a Login with authentication and a CRUD with Firebase as database. <br><br>Link : <a href='https://github.com/williamjkc69/ionic-firebase-crud'>https://github.com/williamjkc69/ionic-firebase-crud</a>",
                link: "https://github.com/williamjkc69/ionic-firebase-crud",
                // image: "ig.gif",
                tag: "Mobile App",
                color: "blue",
                date: "2020-01-01"
              },
              {
                title: "Docker configured to Laravel Environment",
                content:
                  "Configuration to run Laravel 8 env on docker and nginx server <br><br>Link : <a href='https://github.com/williamjkc69/laravel-docker'>https://github.com/williamjkc69/laravel-docker</a>",
                link: "https://github.com/williamjkc69/laravel-docker",
                // image: "ig.gif",
                tag: "library",
                color: "green",
                date: "2019-12-30"
              },
              {
                title: "React Calculator",
                content:
                  "Basic calculator build in React Native <br><br>Link : <a href='https://github.com/williamjkc69/calculator-react-native'>https://github.com/williamjkc69/calculator-react-native</a>",
                link: "https://github.com/williamjkc69/calculator-react-native",
                // image: "ig.gif",
                tag: "Mobile App",
                color: "blue",
                date: "2019-12-30"
              },
              {
                title: "Weather App",
                content:
                  "Node script for get Weather from any City <br><br>Link : <a href='https://github.com/williamjkc69/node-app-wheater'>https://github.com/williamjkc69/node-app-wheater</a>",
                link: "https://github.com/williamjkc69/node-app-wheater",
                // image: "ig.gif",
                tag: "Software",
                color: "red",
                date: "2017-01-02"
              }
              // {
              //   title: "IG_Automation_Bot (Work in progress)",
              //   content:
              //     "Python script for Instagram automation using Instaloader. Used for auto following and DM. Easily configurable through Yaml config files!<br><br>Link : <a href='https://github.com/hbollon/IG_Automation_Bot'>https://github.com/hbollon/IG_Automation_Bot</a>",
              //   link: "https://github.com/hbollon/IG_Automation_Bot",
              //   image: "ig.gif",
              //   tag: "Software",
              //   color: "red",
              //   date: "2020-11-02"
              // },
              // {
              //   title: "Amazon Web Servicesdlib",
              //   content:
              //     "Golang string comparison and edit distance algorithms library, featuring : Levenshtein, LCS, Hamming, Damerau levenshtein (OSA and Adjacent transpositions algorithms), Jaro-Winkler, Cosine, etc.<br><br>Link : <a href='https://github.com/hbollon/go-edlib'>https://github.com/hbollon/go-edlib</a>",
              //   link: "https://github.com/hbollon/go-edlib",
              //   image: "edlib.jpg",
              //   tag: "Library",
              //   color: "blue",
              //   date: "2020-08-25"
              // },
              // {
              //   title: "Gyro'Ball",
              //   content:
              //     "3D labyrinth game project for Android using Unity. Use device gyroscope.<br><br>Link : <a href='https://play.google.com/store/apps/details?id=com.BitsPlease.GyroBall&hl=fr&fbclid=IwAR0itwUAcbpAl3TgkFGiSrQz_CHTRpWjSXTQZqNGPESikdOJWZ6DIrk5qAA'>Google Play</a>",
              //   link:
              //     "https://play.google.com/store/apps/details?id=com.BitsPlease.GyroBall&hl=fr&fbclid=IwAR0itwUAcbpAl3TgkFGiSrQz_CHTRpWjSXTQZqNGPESikdOJWZ6DIrk5qAA",
              //   image: "gyroball.jpg",
              //   tag: "Video Game",
              //   color: "purple",
              //   date: "2020-07-28"
              // },
              // {
              //   title: "GyroscopeControl",
              //   content:
              //     "Unity script used for smooth and customizable object rotation with gyroscope. It include initial calibration with offset, rotation speed, smoothing parameter editable in Unity inspector and debug overlay.<br><br>Link : <a href='https://github.com/hbollon/GyroscopeControl'>https://github.com/hbollon/GyroscopeControl</a>",
              //   link: "https://github.com/hbollon/GyroscopeControl",
              //   image: "",
              //   tag: "Script",
              //   color: "green",
              //   date: "2020-06-17"
              // },
              // {
              //   title: "Urbalog",
              //   content:
              //     "Android adaptation of board game using Nearby Connections API and Java for the LAET<br><br>Link : <a href='https://github.com/hbollon/Urbalog'>https://github.com/hbollon/Urbalog</a>",
              //   link: "https://github.com/hbollon/Urbalog",
              //   image: "urba.jpg",
              //   tag: "Video Game",
              //   color: "purple",
              //   date: "2020-05-19"
              // },
              // {
              //   title: "android-sqlite-toolbox",
              //   content:
              //     "Android java package designed to manage any sqlite database. Includes creation of the db and interactions with it (CRUD), import and export in several file formats (easily adaptable to any other format) and synchronization in http.<br><br>Link : <a href='https://github.com/hbollon/android-sqlite-toolbox'>https://github.com/hbollon/android-sqlite-toolbox</a>",
              //   link: "https://github.com/hbollon/android-sqlite-toolbox",
              //   image: "",
              //   tag: "Library",
              //   color: "blue",
              //   date: "2020-05-08"
              // },
              // {
              //   title: "Le-Parrainage-Boursorama",
              //   content:
              //     "Website built with Laravel. Used to promote and manage sponsorships for a online bank. Hosted on personnal vps.<br><br>Link : <a href='https://le-parrainage-boursorama.fr'>https://le-parrainage-boursorama.fr</a>",
              //   link: "https://le-parrainage-boursorama.fr",
              //   image: "boursoweb.jpg",
              //   tag: "Website",
              //   color: "orange",
              //   date: "2019-09-15"
              // }
            ],
            title: "My projects",
            description: "This is my story"
          }
        },
        {
          slug: "skills",
          title: "skills",
          metadata: {
            items: [
              { title: "VueJS", img: "vuejs.png" },
              { title: "NuxtJS", img: "nuxt.png" },
              { title: "Laravel", img: "laravel.png" },
              { title: "PHP", img: "php.png" },
              { title: "Angular", img: "angular.png" },
              { title: "React", img: "react.png" },
              { title: "Ionic", img: "ionic.png" },
              { title: "Linux", img: "linux.png" },
              { title: "Laravel Nova", img: "nova.png" },
              { title: "HTML", img: "html.png" },
              { title: "CSS", img: "css.png" },
              { title: "Javascript", img: "js.png" },
              { title: "MySql", img: "mysql.png" },
              { title: "Docker", img: "docker.png" },
              { title: "Amazon Web Services", img: "aws.png" },
              { title: "JQuery", img: "jquery.png" },
              { title: "Bootstrap", img: "bootstrap.png" },
              { title: "WordPress", img: "wordpress.png" },
              { title: "Stripe", img: "stripe.png" },
              { title: "Apache", img: "apache.png" },
              { title: "Nginx", img: "nginx.png" },
              { title: "Git", img: "git.png" }
            ],
            title: "Skills",
            description: "Here is What I know"
          }
        },
        {
          slug: "links",
          title: "links",
          metadata: {
            facebook: "https://www.facebook.com/williamjkc69",
            instagram: "https://www.instagram.com/williamjkc69",
            linkedin: "https://www.linkedin.com/in/williamjkc69",
            github: "https://github.com/williamjkc69",
            google: "williamjkc69@gmail.com"
          }
        },
        {
          slug: "user-data",
          title: "user-data",
          metadata: {
            name: "William Urbina",
            status: "Full Stack Developer",
            email: "williamjkc69@gmail.com",
            phone: "+503 6116 8813",
            city: "Cuscatlán, El Salvador",
            lang: "Spanish, English",
            photo: "my-photo.jpeg"
          }
        },
        {
          slug: "description",
          title: "description",
          metadata: {
            pres_first:
              "My name is William Urbina, I am software engineer. Nowadays I am a full stack developer, actually I love web software development and I get experience making what I like every single day, moreover I like to find solutions in best precise and optimal ways for the web pages or web apps to have the best performance possible.",
            pres_second:
              "I have always liked to be part in projects which ask for skill that I do not have because it makes me learn new technologies to put into practice in other projects and innovate with all the solutions I have gotten",
            pres_title: "Who am I ?",
            description: "Hope to know you after",
            title: "About Me"
          }
        },
        {
          slug: "experiences",
          title: "experiences",
          metadata: {
            description: "Professional and Academic",
            title: "Experience",
            professional: [
              {
                year: "12.2019 - Present",
                title: "Full Stack Developer",
                place: "TrezLabs",
                content:
                  "API development, web development, devops and WordPress support"
              },
              {
                year: "05.2021",
                title: "Freelancer",
                place: "Work From Home",
                content: "Frontend Developer"
              }
            ],
            academic: [
              {
                year: "06.2013 - 06.2019",
                title: "Engineering In Computer Science",
                place: "Universidad Don Bosco",
                content: "Specialized in Web Development"
              }
            ]
          }
        }
      ]
    };
  },
  methods: {
    findSlug(slug) {
      return this.posts.find((item) => {
        return item.slug === slug;
      });
    },
    extractFirstObject(objects) {
      if (objects.objects == null) return void 0;
      else return objects.objects[0];
    }
  },
  created() {
    document.body.classList.add("loading");
    this.$nextTick(() => {
      document.body.classList.remove("loading");
      this.isLoaded = true;
    });
  }
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

#app {
  font-family: Montserrat-Regular, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.wrapper {
  height: 100%;
}
</style>
