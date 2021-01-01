<script context="module">
import PageHome from "./pages/Home.svelte";
import Page from "./pages/Page.svelte";

// export const pages = [
//   {
//     name: "Home",
//     path: "/",
//     component: PageHome
//   },
//   {
//     name: "Finance",
//     path: "finance",
//     component: PageFinance
//   },
//   {
//     name: "Math",
//     path: "math",
//     component: PageMath
//   }
// ];

import CompoundInterest from "./components/finance/CompoundInterest.svelte";

import Percent from "./components/math/Percent.svelte";

export const pages = [
  {
    id: "home",
    name: "Home",
    path: "/",
    component: PageHome
  },
  {
    id: "finance",
    name: "Finance",
    path: "finance",
    component: Page,
    components: [
      {
        name: "Compound Interest",
        id: "compoundInterest",
        component: CompoundInterest
      }
    ]
  },
  {
    id: "math",
    name: "Math",
    path: "math",
    component: Page,
    components: [
      {
        name: "Percent",
        id: "percent",
        component: Percent
      }
    ]
  }
];
</script>
