<template>
  <div>
    <header class="tw-bg-gray-100 tw-py-4 tw-mb-16">
      <div class="tw-container">
        <h1>DripCoder</h1>
      </div>
    </header>
    <div class="page-body tw-px-4 md:tw-px-0">
      <div
        class="tw-flex tw-items-center tw-mb-16 banner tw-flex-col md:tw-flex-row"
      >
        <img src="/images/avatar.svg" class="tw-mr-8 tw-mb-4" width="124px" />
        <div>
          <h1 class="tw-text-2xl tw-font-bold">Hey! I'm Kristher Vidal</h1>
          <p class="tw-mb-2 tw-pr-8">
            and I help companies build their web apps through my skills in
            modern web development.
          </p>
          <button
            class="tw-flex tw-text-white tw-bg-green-500 tw-pl-4 tw-pr-8 tw-py-2 tw-rounded-md"
          >
            <img src="/icons/mail.svg" alt="" class="tw-mr-2" />
            <span> Contact </span>
          </button>
        </div>
      </div>
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
      </section>
      <hr class="tw-w-1/12 tw-mb-2 tw-border-t-8 tw-border-black" />
      <section>
        <h1 class="tw-text-2xl tw-font-bold tw-mb-8">Tech Stacks 🖥</h1>
        <section
          v-for="stack in mainTechStacks"
          :key="stack.title"
          class="showcase"
        >
          <div class="footer-border" :style="{ background: stack.color }"></div>
          <h1 class="tw-font-bold tw-text-2xl tw-flex tw-mb-3">
            <img :src="stack.icon" alt="" class="tw-mr-2" />
            {{ stack.title }}
          </h1>
          <p>
            {{ stack.content }}
          </p>
          <div v-show="false" class="tw-flex tw-justify-end">
            <a href="" class="tw-flex">
              <span> Read posts </span>
              <img src="icons/arrow-right.svg" alt="" class="tw-ml-2" />
            </a>
          </div>
        </section>

        <section class="other-tech-stacks tw-mb-4">
          <h1 class="tw-text-2xl tw-font-bold tw-mb-8">Other Tech Stacks</h1>
          <div class="tw-grid tw-grid-cols-2 md:tw-grid-cols-3 tw-gap-4">
            <div
              v-for="stack in otherTechStacks"
              :key="stack.icon"
              class="tw-flex tw-p-2 tw-border-gray-200 tw-border tw-rounded-md"
            >
              <img :src="stack.icon" alt="" class="tw-mr-4" width="24px" />
              <span class="label"> {{ stack.label }}</span>
            </div>
          </div>
        </section>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      mainTechStacks: [
        {
          icon: 'icons/laravel.svg',
          title: 'Laravel',
          color: '#FF0000',
          content:
            'The best PHP Framework handsdown. Laravel gives you the best of flexibility and simplicity. Build your apps fast with out of the box support for multiple technologies'
        },
        {
          icon: 'icons/angular.svg',
          title: 'Angular',
          color: '#F50526',
          content:
            'The best PHP Framework handsdown. Laravel gives you the best of flexibility and simplicity. Build your apps fast with out of the box support for multiple technologies'
        },
        {
          icon: 'icons/vue.svg',
          title: 'VueJs',
          color: '#00B373',
          content:
            'The best PHP Framework handsdown. Laravel gives you the best of flexibility and simplicity. Build your apps fast with out of the box support for multiple technologies'
        }
      ],
      otherTechStacks: [
        {
          icon: '/icons/graphql.svg',
          label: 'GraphQL'
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
        }
      ]
    }
  }
}
</script>
<style lang="postcss" scoped>
.page-body {
  @apply tw-mx-auto;
  max-width: 600px;
}
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
</style>
