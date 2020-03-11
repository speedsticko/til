Editable User Interfaces
-----

Using Vue.js and Tailwindcss
=====
Reference: https://www.binarcode.com/blog/editable-interfaces-with-vuejs-and-tailwind/

* To support sorting you need to have a data representation of your elements that can be rendered generically:
  * You can put the page components in a javascript array and use the special Vue component component.
```
<template>
  <div id="app" class="min-h-screen w-full bg-gray-200">
    <main>
      <component
        v-for="(component, index) in page.components"
        :key="index"
        :is="component.name"
        v-bind="component.props"
      />
    </main>
  </div>
</template>

<script>
import About from "./components/About";
import Contact from "./components/Contact";
import Features from "./components/Features";
import Hero from "./components/Hero";
import Services from "./components/Services";
import Team from "./components/Team";
export default {
  name: "App",
  components: {
    About,
    Contact,
    Features,
    Hero,
    Services,
    Team
  },
  data() {
    return {
      page: {
        components: [
          {
            name: "Hero",
            props: {}
          },
          {
            name: "Features",
            props: {}
          },
          {
            name: "About",
            props: {}
          },
          {
            name: "Team",
            props: {}
          },
          {
            name: "Services",
            props: {}
          },
          {
            name: "Contact",
            props: {}
          }
        ]
      }
    };
  }
};
</script>

<style>
</style>
```
