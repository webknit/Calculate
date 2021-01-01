<script context="module">
import PageHome from "./pages/Home.svelte";
import Page from "./pages/Page.svelte";

import CompoundInterest from "./components/finance/CompoundInterest.svelte";

import Percent from "./components/math/Percent.svelte";

import Height from "./components/unit-conversion/Height.svelte";
import UnitConversionDefault from "./components/unit-conversion/UnitConversionDefault.svelte";
import PensionGoal from "./components/finance/PensionGoal.svelte";

export const pages = [
  {
    id: "home",
    name: "Home",
    path: "/",
    component: PageHome
  },
  {
    id: "units",
    name: "Unit conversion",
    path: "unit-conversion",
    component: Page,
    components: [
      {
        name: "Distance",
        id: "distance",
        component: UnitConversionDefault,
        unit1: "miles",
        unit2: "km",
        amount1: 1,
        units: ["km", "miles", "metres", "yards"],
        sums: {
          miles: {
            km: 1.609344,
            metres: 1609.34,
            yards: 1760
          },
          km: {
            miles: 0.621371,
            metres: 1000,
            yards: 1093.61
          },
          metres: {
            km: 0.001,
            miles: 0.000621371,
            yards: 1.09361
          },
          yards: {
            miles: 0.000568182,
            km: 0.0009144,
            metres: 0.9144
          }
        }
      },
      {
        name: "Length",
        id: "length",
        component: UnitConversionDefault,
        unit1: "cm",
        unit2: "inches",
        amount1: 1,
        units: ["cm", "inches", "feet", "metres"],
        sums: {
          cm: {
            inches: 0.393701,
            feet: 0.0328084,
            metres: 0.01
          },
          inches: {
            cm: 2.54,
            feet: 0.0833333,
            metres: 0.0254
          },
          feet: {
            cm: 30.48,
            inches: 12,
            metres: 0.3048
          },
          metres: {
            cm: 100,
            inches: 39.3701,
            feet: 3.28084
          }
        }
      },
      {
        name: "Height (ft/inch to cm)",
        id: "height",
        component: Height
      },
      {
        name: "Weight",
        id: "weight",
        component: UnitConversionDefault,
        unit1: "stone",
        unit2: "kg",
        amount1: 1,
        units: ["stone", "kg", "pounds"],
        sums: {
          stone: {
            kg: 6.35029,
            pounds: 14
          },
          kg: {
            stone: 0.157473,
            pounds: 2.20462
          },
          pounds: {
            kg: 0.453592,
            stone: 0.0714286
          }
        }
      }
    ]
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
      },
      {
        name: "Pension Goal",
        id: "pensionGoal",
        component: PensionGoal
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
        name: "% of a number",
        id: "percent-number",
        component: Percent
      }
    ]
  }
];
</script>
