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
        // phone: "+503 6116 8813",
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
                title: "tPromise casino game (wip)",
                content: `Promise Smart Contract Casino, you can play in win tPromise tokens
                <br> <b>Tech:</b> React, NextJs, Web3, Tailwind`,
                image: "casino.png",
                tag: "Web3 App",
                color: "green",
                // date: "2022-02-15",
              },
              {
                title: "tPromise migration",
                content: `App to exchange tPromise crypto V1 to V2
                <br> <b>Tech:</b> React, NextJs, Web3, Tailwind`,
                image: "promise_migration.png",
                tag: "Web3 App",
                color: "green",
                date: "2022-02-15",
              },
              {
                title: "RentVault",
                content: `House rentals, app implements Stripe payments with one pay or recurring payment
                <br> <b>Tech:</b> Laravel, JQuery, Stripe`,

                image: "rent.png",
                tag: "website",
                color: "black",
                date: "2022-01-5"
              },
              {
                title: "tPromise",
                content: `App to staking pool with tPromise crypto
                <br> <b>Tech:</b> React, NextJs, Web3, Tailwind`,
                image: "promise.png",
                tag: "NTF webapp",
                color: "blue",
                date: "2021-12-15"
              },
              {
                title: "Vue Dropdown (WIP)",
                content: `Vue package that implements a beautiful dropdown with multiple options and very customize
                <br> <b>Tech:</b> Vue, SCSS
                <br><br>Link : <a target='_blank' href='https://www.npmjs.com/package/vue-dropdown-multiselect'>Visit Site</a>`,
                link: "https://www.npmjs.com/package/vue-dropdown-multiselect",
                image: "dropdown.gif",
                tag: "package",
                color: "red"
                // date: "2021-05-15"
              },
              {
                title: "JustYours",
                content: `JustYours exclusive adult content creator platform 
                  <br> <b>Tech:</b> Vue, Vuex, Nuxt, Web3, Tailwind, Laravel, MongoDB, PusherJs
                  <br><br>Link : <a target='_blank' href='https://justyours.me/'>Visit Site</a>`,
                link: "https://justyours.me/",
                image: "jy.png",
                tag: "NTF webapp",
                color: "purple",
                date: "2022-01-27"
              },
              {
                title: "Symple",
                content: `Symple manages your certifications for single or multiple properties nationwide 
                  <br> <b>Tech:</b> Vue, Vuex, Bootstrap, Laravel, MySQL, PusherJs, InertiaJs, Stripe
                  <br><br>Link : <a <a target='_blank' href='https://symple.co.uk/'>Visit Site</a>`,
                link: "https://symple.co.uk/",
                image: "symple.png",
                tag: "website",
                color: "red",
                date: "2021-05-15"
              },
              {
                title: "SCF Music",
                content: `Webapp to create events and concerts. It's and API too for mobile app showing all events
                  <br> <b>Tech:</b> Laravel Nova, Laravel, Bootstrap, MySQL
                  <br><br>Link : <a <a target='_blank' href='http://music.forwardforce.io'>Visit Site</a>`,
                link: "http://music.forwardforce.io",
                image: "scf.png",
                tag: "webapp",
                color: "green",
                date: "2020-03-1"
              },
              {
                title: "Miracle",
                content: `Informative Website
                  <br> <b>Tech:</b> WordPress, Elementor, Custom Plugins
                  <br><br>Link : <a <a target='_blank' href='https://www.miracle.co.il/'>Visit Site</a>`,
                link: "https://www.miracle.co.il/",
                image: "miracle.png",
                tag: "website",
                color: "pink",
                date: "2020-07-1"
              },
              {
                title: "Weather App",
                content:
                  "NodeJs script for get Weather from any City <br><br>Link : <a href='https://github.com/williamjkc69/node-app-wheater'>https://github.com/williamjkc69/node-app-wheater</a>",
                link: "https://github.com/williamjkc69/node-app-wheater",
                // image: "ig.gif",
                tag: "Software",
                color: "red",
                date: "2019-01-02"
              }
            ],
            title: "My projects",
            description: "I share my Background"
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
              // { title: "Angular", img: "angular.png" },
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
              { title: "Tailwind", img: "tailwind.png" },
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
