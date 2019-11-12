<template>
  <div class="home">
  <v-parallax
    dark
    height="650"
    src="@/assets/imgs/Step8.jpg"
  >
  
    <v-row
      align="center"
      justify="center"
    >

      <v-col class="text-center" cols="12" sm="12">
        <v-img class="mx-auto" height="200" width="200" src="@/assets/imgs/logo.png"></v-img>
        <h1 class="display-3 font-weight-bold mb-4">FEMORA</h1>
        <h4 class="subheading">Unending Creativity!</h4>
      </v-col>

    </v-row>
  </v-parallax>

  <!-- add a bar -->

  <v-container class="mt-3 mb-10">
    <v-row class="my-5">
      <v-col cols="12">
        <h1 class="h1-responsive text-center">Our Services</h1>
        <p class="text-center">We offer professional services in the various categories</p>
      </v-col>

      <v-col cols="12" md="6" sm="6" class="text-center pt-5 mt-5">
        <v-icon color="green accent-4" size="100">mdi-identifier</v-icon>
        <h2 class="display-1 my-4">Branding</h2>
        <p class="mt-3">
          Lorem ipsum dolor sit amet consectetur, 
          adipisicing elit. Quibusdam consequuntur 
          recusandae quo voluptas iste, praesentium 
          iusto nobis, culpa harum quam rem tempore 
          quaerat. Modi tempore, quasi quae voluptates 
          a nesciunt!
        </p>
      </v-col>

      <v-col cols="12" md="6" sm="6" class="text-center pt-5 mt-5">
        <v-icon color="green accent-4" size="100">mdi-desktop-mac-dashboard</v-icon>
        <h2 class="display-1 my-4">Web Development</h2>
        <p class="mt-3">
          Lorem ipsum dolor sit amet consectetur, 
          adipisicing elit. Quibusdam consequuntur 
          recusandae quo voluptas iste, praesentium 
          iusto nobis, culpa harum quam rem tempore 
          quaerat. Modi tempore, quasi quae voluptates 
          a nesciunt!
        </p>
      </v-col>

    </v-row>

    <v-row>
      <v-responsive>
       <v-sheet
    class="mx-auto"
    elevation="0"
    color="grey lighten-5"
  >
    <v-slide-group
      v-model="model"
      class="pa-4"
      center-active
      
    >
      <v-slide-item 
        v-slot:default="{ active, toggle }"
        v-for="item in serviceCards"
        :key="item.title"
      >

        <v-card
          :color="active ? 'light-green accent-1' : 'white'"
          max-width="270"
          class="mx-auto ml-4 my-2"
          @click="toggle"
        >
          <v-list-item>
            <v-list-item-avatar color="grey"></v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="headline">Web Design</v-list-item-title>
              <v-list-item-subtitle>Cool and Responsive Layouts</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="194"
          ></v-img>

          <v-card-text>
            Visit ten places on our planet that are undergoing the biggest changes today.
          </v-card-text>

          
        </v-card>

      </v-slide-item>
    </v-slide-group>
  </v-sheet>
      </v-responsive>
    </v-row>
  </v-container>


<!-- Portfolio Section -->
  <v-parallax
    height="300" 
    src="@/assets/imgs/Step8.jpg"
  >

    <!-- Portfolio using bottom v-sheet -->
    <v-row
      align="center"
      justify="center"
    >

      <v-col class="text-center" cols="12" sm="12">
        <h1 class="display-2 my-6">Our Job Speaks For us</h1>
        <v-btn
          color="green"
          dark
          rounded="true"
          @click="sheet = !sheet"
        >
          View Our Portfolio
        </v-btn>

      </v-col>

    </v-row>
      


    <v-bottom-sheet 
      v-model="sheet" 
      persistent
      eager="true"
    >
    
      <v-sheet class="text-center">
        <v-btn
          class="mt-6 mb-6"
          text
          color="green accent-4"
          @click="sheet = !sheet"
        >close</v-btn>


        <v-carousel>
          <v-carousel-item
            v-for="(color, i) in colors"
            :key="color"
          >
            <v-sheet
              :color="color"
              height="100%"
              tile
            >
              <v-row
                class="fill-height"
                align="center"
                justify="center"
              >
                <div class="display-3">Slide {{ i + 1 }}</div>
              </v-row>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>

      </v-sheet>
    </v-bottom-sheet>
  <!-- /Portifolio v-sheet -->

  </v-parallax>
<!-- Portfolio Section -->



<!-- Portfolio Section -->
  <v-container>
    <!-- Portfolio using bottom v-sheet -->
    <v-row no-gutters="" class='my-10'>
      <v-col class="my-3 text-center" cols="12">
        <h1 class="display-1">Pricing</h1>
        <p class="body">Lorem ipsum dolor sit amet consectetur, adipisicing elit. </p>
      </v-col>
      <v-col class="my-3 mx-auto" cols="12" sm="6" md="4" lg="3" xl="2" v-for="(slide, i) in slides"
          :key="i">


        <v-hover v-slot:default="{ hover }">
          <v-card class="mx-auto" max-width="250" :elevation="hover ? 12 : 2">
            <v-card-text>
            <div class="text-center">
              <h6 class="subtitle-2 font-weight-black">Starter</h6>
              <h2 class="mb-7 mt-4"> $ <span class="display-3 font-weight-black">3,000</span></h2>
              <v-divider class="mx-4" :inset="inset"></v-divider>
            </div>

            <div>
              <v-list dense>
                <v-list-item-group v-model="item" color="primary">
                  <v-list-item
                    v-for="(item, i) in items"
                    :key="i"
                  >
                    <v-list-item-icon>
                      <v-icon color="green accent-4">mdi-check-decagram</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                      <v-list-item-title>{{item.text}}</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list-item-group>
              </v-list>
            </div>
            </v-card-text>

            <v-card-actions>
              <v-btn
                flat
                outlined
                rounded
                color="green darken-4"
                class="mx-auto mb-4"
              >
                Learn More
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-hover>

        

      </v-col>
    </v-row>
    <!-- /Portifolio v-sheet -->
  </v-container>
<!-- Portfolio Section -->


<div class="my-10 grey lighten-3">
<!-- Testimonial -->
<v-container>
  <div class="text-center my-10">
    <h1 class="display-1">Testimonial</h1>
    <p class="body my-3">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ex harum s</p> 
  </div>
  <v-row align="center" class="my-10">
    <v-item-group
      v-model="window"
      class="shrink mr-6"
      mandatory
      tag="v-flex"
    >
      <v-item
        v-for="n in length"
        :key="n"
        v-slot:default="{ active, toggle }"
      >
        <div>
          <v-btn
            :input-value="active"
            icon
            @click="toggle"
          >
            <v-icon>mdi-record</v-icon>
          </v-btn>
        </div>
      </v-item>
    </v-item-group>

    <v-col>
      <v-window
        v-model="window"
        class="elevation-1"
        vertical
      >
        <v-window-item
          v-for="n in length"
          :key="n"
        >
          <v-card flat>
            <v-card-text>
              <v-row class="mb-4" align="center">
                <v-avatar color="grey" class="mx-4"></v-avatar>
                <strong class="title">Title {{ n }}</strong>
                <v-spacer></v-spacer>
                <v-btn icon>
                  <v-icon>mdi-account</v-icon>
                </v-btn>
              </v-row>

              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
              </p>
            </v-card-text>
          </v-card>
        </v-window-item>
      </v-window>
    </v-col>
  </v-row>
</v-container>
<!-- End Testimonial -->
</div>


<!-- recent blogs -->
<v-container>
  <v-row class="my-10" align="center" justify="center">
    <v-col cols="12" md="3" class="text-center">
      <h1 class="display-1">Recent Blog</h1>
      <p class="subtitle-1">Lorem ipsum dolor sit amet </p>
    </v-col>

    <v-col cols="12" md="9">
      <v-row>
        <v-col
          cols="12"
          sm="4"
          md="4"
          v-for="i in 3"
          :key="i"
        >

          <v-card>
            <v-list-item>
              <v-list-item-avatar color="grey"></v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title class="headline">Our Changing Planet</v-list-item-title>
                <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>

            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
              height="194"
            ></v-img>

            <v-card-text>
              Visit ten places on our planet that are undergoing the biggest changes today.
            </v-card-text>

          
              <v-btn
                tile
                height="50"
                block
                dark
                ripple
                color="green accent-4"
              >
                Read More
                <v-spacer></v-spacer>

                <v-icon>mdi-greater-than</v-icon>
              </v-btn>
            
          </v-card>

        </v-col>
      </v-row>
    </v-col>
  </v-row>
</v-container>
<!-- end reccent blog -->


<!-- ads -->
<!-- end ads -->

<section class="mt-10 grey lighten-3">
<!-- contact us -->
<v-container>
  <v-row class="my-10">
    <v-col cols="12">
      <div class="text-center">
        <h1 class="subtitle-1">Giving your brand all that it deserves is all we do</h1>
        <h1 class="display-1 font-weight-bold mb-5">You Can Keep In Touch<span class="font-weight-light"> With Us</span></h1>
      </div>
    </v-col>
  </v-row>

  <v-row class="my-10" align="center">
    <v-col cols="12" md="4" class="text-center">
      <h1 class="display-2 font-weight-bold">FEMORA</h1>
      <p class="body mt-3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Perferendis, sapiente beatae fugit no sapiente beatae fugit no sapiente beatae fugit no</p>
      <div>
        <p class="body">
          <v-icon right large>mdi-map-marker</v-icon>
          Bonny Isald, Rivers State, Nigeria
        </p>
        <p class="body">
          <v-icon right large>mdi-map-marker</v-icon>
          Bonny Isald, Rivers State, Nigeria
        </p>
        <p class="body mt-4">
          <v-icon right large>mdi-map-marker</v-icon>
          Bonny Isald, Rivers State, Nigeria
        </p>
      </div>

      <div class="ma-6">
        <v-btn class="mr-2" fab depressed small>
          <v-icon>mdi-facebook</v-icon>
        </v-btn>

        <v-btn class="mr-2" fab depressed small>
          <v-icon>mdi-twitter</v-icon>
        </v-btn>

        <v-btn class="mr-2" fab depressed small>
          <v-icon>mdi-dribbble</v-icon>
        </v-btn>

        <v-btn class="mr-2" fab depressed small>
          <v-icon>mdi-instagram</v-icon>
        </v-btn>

        <v-btn class="mr-2" fab depressed small>
          <v-icon>mdi-google-plus</v-icon>
        </v-btn>
      </div>
    </v-col>

    <v-col cols="12" md="8">
      <v-form
        class="mx-10"
        ref="form"
        v-model="valid"
        lazy-validation
      >
        <v-text-field
          v-model="name"
          :counter="10"
          :rules="nameRules"
          label="Name"
          required
        ></v-text-field>

        <v-text-field
          v-model="email"
          :rules="emailRules"
          label="E-mail"
          required
        ></v-text-field>

        <v-textarea
          label="Message/Inquiry"
          auto-grow
        ></v-textarea>

        <v-btn
          class="mt-3"
          dark
          depressed
          color="blue darken-2"
        >
          <v-icon left>
            mdi-send-circle-outline
          </v-icon>
          Submit
        </v-btn>
      </v-form>
    </v-col>
  </v-row>
</v-container>
<!-- end contact us -->
</section>


<!-- footer -->
<v-footer
    padless
  >
    <v-row
      justify="center"
      no-gutters
    >
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="my-2"
      >
        {{ link }}
      </v-btn>
      <v-col
        class="black py-4 text-center white--text"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Femora</strong>
      </v-col>
    </v-row>
  </v-footer>
<!-- end footer -->

  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data() {
    return {
      sheet: false,
      serviceCards: [
        { title: 'Web Design', intro: 'Lorem', image: '' },
        { title: 'Web Design', intro: 'Lorem', image: '' },
        { title: 'Web Design', intro: 'Lorem', image: '' },
        { title: 'Web Design', intro: 'Lorem', image: '' },
        { title: 'Web Design', intro: 'Lorem', image: '' },
      ],
      colors: [
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
      items: [
        { text: 'Real-Time', icon: 'mdi-clock' },
        { text: 'Audience', icon: 'mdi-account' },
        { text: 'Conversions', icon: 'mdi-flag' },
      ],
      slides: [
          'First',
          'Second',
          'Third',
      ],
      length: 5,
      window: 0,
    }
  },
}
</script>
