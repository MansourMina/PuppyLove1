<template>
  <div>
    <v-carousel :show-arrows="false" hide-delimiters cycle interval="3000">
      <v-carousel-item
        v-for="(item, i) in items"
        :key="i"
        :src="item.src"
      ></v-carousel-item>
    </v-carousel>
    <span class="text-h4 d-flex justify-center my-3 green--text"
      >Basset Hound Club of America
    </span>

    <div class="d-block text-center">
      <v-btn class="ma-2" color="green darken-4 white--text">
        MEMBER LOGIN
      </v-btn>
      <v-btn to="/member" class="ma-2" color="green darken-4 white--text">
        BECOME A MEMBER
      </v-btn>
      <v-btn class="ma-2" color="green darken-4 white--text">
        EVENTS
      </v-btn>
      <v-btn class="ma-2" color="green darken-4 white--text">
        FIND A DOG
      </v-btn>
    </div>
    <v-sheet class="mx-auto my-2" width="50%">
      <div class="text-justify">
        Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
        eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
        voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
        clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
        amet.
      </div>
    </v-sheet>
    <div class="d-flex flex-wrap justify-center">
      <DogView v-for="d of dogs" :key="d.id" :dog="d" />
    </div>
  </div>
</template>

<script>
import DogView from '@/components/DogView.vue';
export default {
  name: 'Home',
  data() {
    return {
      items: [
        {
          src:
            'https://www.rover.com/blog/wp-content/uploads/2018/12/basset-hound-wallpaper-hd-2560x1440-214117.jpg',
        },
        {
          src:
            'https://www.welpen.de/cms/wp-content/uploads/2019/01/basset-hound-1.jpg',
        },
        {
          src:
            'https://loveandkissespetsitting.net/wp-content/uploads/2017/10/Basset-Hounds-3-of-them.jpg',
        },
      ],
      dogs: [
        {
          id: 1,
          name: 'Francis',
          image:
            'https://www.edogs.de/magazin/wp-content/uploads/basset-hound-auf-wiese.jpg',
        },
        {
          id: 2,
          name: 'Karambo',
          image:
            'https://www.zooroyal.at/magazin/wp-content/uploads/2018/02/basset-hound-760x570.jpg',
        },
        {
          id: 3,
          name: 'Mr. Phil',
          image:
            'https://mediafiles.mein-haustier.de/wp-content/uploads/2019/01/shutterstock_755551105-komprimiert-1270x847.jpg',
        },
      ],
    };
  },
  components: {
    DogView,
  },
};
</script>
