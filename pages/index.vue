<template>
  <div>
    <header class="tw-py-4 tw-bg-green-500 navigation-bar">
      <div class="tw-container">
          <h1 class="tw-font-bold tw-text-3xl tw-text-white">Drip Coder(WIP)</span></h1>
      </div>
    </header>
    <div class="hero-block">
      <div class="tw-container">
        <div class="md:tw-w-2/3">
          <div
            class="tw-flex tw-items-center  tw-flex-col md:tw-flex-row"
          >
          <div>
          <h1 class="tw-text-5xl tw-font-bold tw-mb-8">
              Let’s
             <span class="tw-bg-green-500 tw-inline-block tw-py-2 tw-px-1 tw-text-white">
              Build Apps
               </span>
              <span class="tw-block">
                Together
              </span>
          </h1>

        <p class="tw-mb-4 tw-text-lg">
            Hey! I am Kristher, A Full Stack Developer from 🇵🇭.
            With more than 5 Years of Experience in Web Development, I helped teams and companies build exciting apps on the Web.
          </p>
          <p class="tw-mb-4">
            Do you need help with your next big project? Smash the Contact Button!
          </p>
          <popup-email></popup-email>
          </div>
            <!-- <img
              src="/images/avatar.svg"
              class="tw-mr-8 tw-mb-4 tw-shadow-lg tw-rounded-full"
              width="124px"
            /> -->
          </div>
        </div>
      </div>
    </div>
    <div class="tw-container">
      <div class="page-body">
        <section class="about-me tw-mb-8">
          <h1 class="tw-text-2xl tw-font-bold tw-mb-8">About Me 👨🏻‍💻</h1>
          <p class="tw-mb-4">
            Developing Websites since 2013, I have gained profound skills in
            building websites using modern tools and technologies.
          </p>
          <p class="tw-mb-4">
            With skills in Laravel, Angular, Vue with a mix of basic DevOps, I
            helped companies developed and deploy their web apps in the cloud.
          </p>
          <div class="tw-flex">
            <a
      class="tw-inline-flex  tw-mr-2 tw-py-1 tw-px-4 tw-border tw-border-gray-100"
               href="https://www.linkedin.com/in/kristher-vidal/" target="_blank">
              <img src="/icons/linkedin.svg" alt="" width="16px" class="tw-mr-2">
              LinkedIn
            </a>
            <a
      class="tw-inline-flex  tw-items-center tw-py-1  tw-px-4 tw-border tw-border-gray-100"
               href="https://github.com/kristher1619" target="_blank">
              <img src="/icons/github.svg" alt="" width="16px" class="tw-mr-2">
              Github
            </a>
          </div>
        </section>
        <hr class="tw-w-1/12 tw-mb-2 tw-border-t-8 tw-border-black"/>
        <section>
          <h1 class="tw-text-2xl tw-font-bold tw-mb-8">Tech Stacks 🖥</h1>
          <section
            v-for="stack in mainTechStacks"
            :key="stack.title"
            class="showcase"
          >
            <div class="footer-border" :style="{ background: stack.color }"></div>
            <h1 class="tw-font-bold tw-text-2xl tw-flex tw-mb-3">
              <img :src="stack.icon" alt="" class="tw-mr-2" width="32px"/>
              {{ stack.title }}
            </h1>
            <p>
              {{ stack.content }}
            </p>
            <div v-show="false" class="tw-flex tw-justify-end">
              <a href="" class="tw-flex">
                <span> Read posts </span>
                <img src="icons/arrow-right.svg" alt="" class="tw-ml-2"/>
              </a>
            </div>
          </section>
          <section class="other-tech-stacks tw-mb-4">
            <h1 class="tw-text-2xl tw-font-bold tw-mb-8">Other Tech and Tools I Use</h1>
            <div class="tw-grid tw-grid-cols-2 md:tw-grid-cols-3 tw-gap-4">
              <div
                v-for="stack in otherTechStacks"
                :key="stack.icon"
                class="tw-flex tw-p-2 tw-border-gray-200 tw-border tw-rounded-md"
              >
                <img :src="stack.icon" alt="" class="tw-mr-4" width="24px"/>
                <span class="label"> {{ stack.label }}</span>
              </div>
            </div>
          </section>
        </section>
      </div>
    </div>
    <site-footer></site-footer>

  </div>
</template>

<script>
import SiteFooter from "~/components/SiteFooter";
import PopupEmail from "~/components/PopupEmail";

export default {
  name: 'IndexPage',
  components: { PopupEmail, SiteFooter },
  data() {
    return {
      mainTechStacks: [
        {
          icon: 'icons/laravel.svg',
          title: 'Laravel',
          color: '#FF0000',
          content:
            'The best PHP Framework hands down. Laravel gives you the best of flexibility and simplicity. Build your apps fast with out of the box support for multiple technologies'
        },
        {
          icon: 'icons/angular.svg',
          title: 'Angular',
          color: '#F50526',
          content:
            'Ah yes! The grand daddy of all modern frameworks!. ' +
            'If you are the OOP kind of guy, you will definitely love this framework.' +
            'For me, this is the javascript framework that makes sense on how you architect your enterprise application.'
        },
        {
          icon: 'icons/vue.svg',
          title: 'VueJs',
          color: '#00B373',
          content:
            'If you are overwhelmed with Angular, Vue got you covered. ' +
            'Developers love VueJS for its simplicity and beautiful syntax. ' +
            'Many prefer Vue because it can be used to build enterprise apps without the massive boilerplate.'
        }
      ],
      otherTechStacks: [
        {
          icon: '/icons/graphql.svg',
          label: 'GraphQL'
        },
        {
          icon: '/icons/rxjs.svg',
          label: 'RxJs'
        },
        {
          icon: '/icons/tailwind.svg',
          label: 'Tailwind'
        },
        {
          icon: '/icons/mysql.svg',
          label: 'MySQL'
        },
        {
          icon: '/icons/javascript.svg',
          label: 'Javascript'
        },
        {
          icon: '/icons/git.svg',
          label: 'Git'
        },
        {
          icon: '/icons/css.svg',
          label: 'CSS'
        },
        {
          icon: '/icons/github.svg',
          label: 'GitHub'
        },
        {
          icon: '/icons/html.svg',
          label: 'HTML5'
        },
        {
          icon: '/icons/typescript.svg',
          label: 'Typescript'
        },
        {
          icon: '/icons/c-sharp.svg',
          label: 'C#'
        },
        {
          icon: '/icons/nuxt.svg',
          label: 'NuxtJS'
        }
      ]
    };
  },
  head: {
    title: 'Drip Coder - Kristher Vidal'
  }
};
</script>
<style lang="postcss" scoped>
.showcase {
  @apply tw-border-gray-200 tw-border tw-rounded-md tw-p-4 tw-mb-8 tw-relative tw-bg-white;

  .footer-border {
    display: block;
    content: '';
    position: absolute;
    top: 0;
    bottom: -5px;
    width: 100%;
    left: 0;
    z-index: -1;
    @apply tw-rounded-bl-md tw-rounded-br-md;
  }
}
.navigation-bar {
  height: 60px;
}
.hero-block {
  @apply tw-border-b tw-border-gray-200 tw-py-12 tw-mb-8 tw-relative tw-flex tw-items-center;
  @screen lg {
    background: url(/icons/header-bg.svg) no-repeat right center;
    height: 550px;
  }

}
</style>
