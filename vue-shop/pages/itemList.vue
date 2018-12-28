<template>
  <v-container grid-list-xl>
    <v-layout v-bind="binding">

      <v-flex>
        <v-card>
        <v-img
          class="white--text"
          height="200px"
          src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
        >
          <v-container fill-height fluid>
            <v-layout fill-height>
              <v-flex xs12 align-end flexbox>
                <span class="headline">아이폰X 128GB</span>
              </v-flex>
            </v-layout>
          </v-container>
        </v-img>

        <v-card-title>
          <div>
            <span class="grey--text">닉네임</span><br>
            <span>서울시 동작구</span><br>
            <span>600.000원</span>
          </div>
        </v-card-title>
        <v-card-actions>
          <v-btn flat color="orange">Share</v-btn>
          <v-btn flat color="orange">Explore</v-btn>
        </v-card-actions>
      </v-card>
      </v-flex>


      <v-flex>
        <v-card>
        <v-img
          class="white--text"
          height="200px"
          src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
        >
          <v-container fill-height fluid>
            <v-layout fill-height>
              <v-flex xs12 align-end flexbox>
                <span class="headline">Top 10 Australian beaches</span>
              </v-flex>
            </v-layout>
          </v-container>
        </v-img>

        <v-card-title>
          <div>
            <span class="grey--text">Number 10</span><br>
            <span>Whitehaven Beach</span><br>
            <span>Whitsunday Island, Whitsunday Islands</span>
          </div>
        </v-card-title>
        <v-card-actions>
          <v-btn flat color="orange">Share</v-btn>
          <v-btn flat color="orange">Explore</v-btn>
        </v-card-actions>
      </v-card>
      </v-flex>



      <v-flex>
        <v-card dark color="accent">
          <v-card-text>three</v-card-text>
        </v-card>
      </v-flex>

      <v-flex>
        <v-card dark color="accent">
          <v-card-text>three</v-card-text>
        </v-card>

      </v-flex>

      <v-flex>
        <v-card dark color="accent">
          <v-card-text>three</v-card-text>
        </v-card>

      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    computed: {
      binding () {
        const binding = {}

        if (this.$vuetify.breakpoint.mdAndUp) binding.column = true

        return binding
      }
    }
  }
</script>
