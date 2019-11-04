<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex xs12>
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        ></v-img>
      </v-flex>

      <v-flex mb-4>
        <h1 class="display-2 font-weight-bold mb-3">
          Welcome to Vuetify
        </h1>
        <p class="subheading font-weight-regular">
          Insert the org chart here... panning: {{ chart.isPan }}
          <organization-chart :datasource="chart.chartData" :pan="chart.isPan">
            
          </organization-chart>
        </p>
      </v-flex>

      <v-flex
        mb-5
        xs12
      >
        <h2 class="headline font-weight-bold mb-3">What's next?</h2>

        <v-layout justify-center>
          <a
            v-for="(next, i) in whatsNext"
            :key="i"
            :href="next.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ next.text }}
          </a>
        </v-layout>
      </v-flex>

      <v-flex
        xs12
        mb-5
      >
        <h2 class="headline font-weight-bold mb-3">Important Links</h2>

        <v-layout justify-center>
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ link.text }}
          </a>
        </v-layout>
      </v-flex>

      <v-flex
        xs12
        mb-5
      >
        <h2 class="headline font-weight-bold mb-3">Ecosystem</h2>

        <v-layout justify-center>
          <a
            v-for="(eco, i) in ecosystem"
            :key="i"
            :href="eco.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ eco.text }}
          </a>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import OrganizationChart from 'vue-organization-chart';

import 'vue-organization-chart/dist/orgchart.css';

export default {
  components: {
    OrganizationChart,
  },
  data: () => ({
    ecosystem: [
      {
        text: 'vuetify-loader',
        href: 'https://github.com/vuetifyjs/vuetify-loader',
      },
      {
        text: 'github',
        href: 'https://github.com/vuetifyjs/vuetify',
      },
      {
        text: 'awesome-vuetify',
        href: 'https://github.com/vuetifyjs/awesome-vuetify',
      },
    ],
    importantLinks: [
      {
        text: 'Documentation',
        href: 'https://vuetifyjs.com',
      },
      {
        text: 'Chat',
        href: 'https://community.vuetifyjs.com',
      },
      {
        text: 'Made with Vuetify',
        href: 'https://madewithvuejs.com/vuetify',
      },
      {
        text: 'Twitter',
        href: 'https://twitter.com/vuetifyjs',
      },
      {
        text: 'Articles',
        href: 'https://medium.com/vuetify',
      },
    ],
    whatsNext: [
      {
        text: 'Explore components',
        href: 'https://vuetifyjs.com/components/api-explorer',
      },
      {
        text: 'Select a layout',
        href: 'https://vuetifyjs.com/layout/pre-defined',
      },
      {
        text: 'Frequently Asked Questions',
        href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
      },
    ],
    chart: {
      chartData: {
        id: '1',
        name: 'L L',
        title: 'CEO',
        children: [
          { id: '2', name: 'B', title: 'COO' },
          {
            id: '3',
            name: 'C',
            title: 'CTO',
            children: [
              { id: '5', name: 'C A', title: 'Dev Manager' },
              { id: '6', name: 'C B', title: 'BA Manager' },
            ],
          },
          { id: '4', name: 'D', title: 'CFO' },
          {
            id: '7',
            name: 'E',
            title: 'CFO',
            children: [
              { id: '5', name: 'C A', title: 'Dev Manager' },
              { id: '5', name: 'C A', title: 'Dev Manager' },
              { id: '5', name: 'C A', title: 'Dev Manager' },
              { id: '5', name: 'C A', title: 'Dev Manager' },
              {
                id: '7',
                name: 'E',
                title: 'CFO',
                children: [
                  { id: '5', name: 'C A', title: 'Dev Manager' },
                  { id: '5', name: 'C A', title: 'Dev Manager' },
                  { id: '5', name: 'C A', title: 'Dev Manager' },
                  { id: '5', name: 'C A', title: 'Dev Manager' },
                ],
              },
            ],
          },
        ],
      },
      isPan: true,
      isZoom: true,
    },
  }),
};
</script>
