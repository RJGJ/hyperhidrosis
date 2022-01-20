<script setup lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination } from 'swiper';
import { ref } from 'vue';

import 'swiper/css/pagination';


const testimonialData = ref([
  {
    name: "Liat A.",
    imgUrl:
      "https://s3-media0.fl.yelpcdn.com/photo/3WTDD4PlOscL7l0RReBbsg/60s.jpg",
    address: "Encino, Los Angeles, CA",
    content:
      "I have to leave a review for the girls that works at the My Botox LA Med Spa because I am SOOO over the moon happy!! I originally got Botox on my forehead lines & frown lines at a different spa and I came out completely traumatized. 6 months later I decided to go to My Botox LA Med Spa after getting recommendations. I firstly met with Adriana (the receptionist) who was SO sweet. After telling her about my experience at a different spa she made me feel so safe and actually explained the ENTIRE process to me. Adriana took me to Albinas room (the cosmetic nurse) and explained to her my fears and Albina was so incredibly patient with me. I SERIOUSLY recommend this Med Spa. The whole point of getting Botox is to feel better in your own skin and Adriana and Albina did just that!! Thank you so much  see you in a few months",
  },
  {
    name: "Monica M.",
    imgUrl:
      "https://s3-media0.fl.yelpcdn.com/assets/srv0/yelp_styleguide/514f6997a318/assets/img/default_avatars/user_60_square.png",
    address: "Sylmar, CA",
    content:
      "I highly recommend My Botox La  I come here to get my face refreshed Adriana is always very nice and Yana is amazing!! I always love my results!!!!",
  },
  {
    name: "Emina M.",
    imgUrl:
      "https://s3-media0.fl.yelpcdn.com/photo/B99HAujHf33BFrjdPbvyeA/60s.jpg",
    address: "West Hollywood, Los Angeles, CA",
    content:
      "Absolutely love this place! I am so happy with my Botox and filler, can't wait to try the other treatments they offer. The staff is so sweet, Yana was so precise and gentle, my results look ahhmazing!! The office is so cute and kept very clean! So glad I found this Med spa for all my beauty services!",
  },
  {
    name: "Sophie T.",
    imgUrl:
      "https://s3-media0.fl.yelpcdn.com/photo/_GeTxmO41IxURMRJxh-8ng/60s.jpg",
    address: "North Hollywood, Los Angeles, CA",
    content:
      "Yana is the absolute best! I was deathly afraid of needles when I first started getting Botox. Yana is so calming, gentle, and has taken all of my needle anxiety away. I expressed from the beginning that I wanted a very conservative amount of Botox and didn't want to lose too much expression, and that's exactly what I got--just enough to make my forehead smooth and look well rested, not frozen or unnatural. Yana and her staff are so kind, accommodating, and honest. Living in Los Angeles there are soo many med spas, and believe me, I've tried quite a few of them, but nowhere compares to My Botox LA!!",
  },
  {
    name: "Lola K.",
    imgUrl:
      "https://s3-media0.fl.yelpcdn.com/photo/7cvOUvOyuSBCnvwW6tss2Q/60s.jpg",
    address: "Los Angeles, CA",
    content:
      "I can't rave about Albina enough. To have anything done to our face is a decision not to be made lightly so naturally we want to make sure that everything is done by a knowledgeable and experienced professional.  Albina understands how to enhance features and eliminate the flaws for a beautiful look. She explains what needs to be done, why and what to expect. I didn't know that one side of my upper lip is longer and it gave me a weird crooked droopy mouth look until she explained it to me and corrected it with filler to where I am no longer self conscious to smile and not shy away from photos. That was after someone else injected botox in it just because i said that's what i needed - as if i knew better. Another person left me with a perpetually surprised eyebrows for weeks. At this point I would not trust anyone else to touch my face and always trust Albina to fill me in on the latest techniques and products if she thinks they would be helpful but you can always be confident that she will not recommend or sell you anything which will not be the right solution for your particular issue. Book a session with her!",
  },
]);

</script>
<template>
  <swiper
    :space-between="30"
    :breakpoints="{ 1200: { slidesPerView: 3 } }"
    :pagination="{ clickable: true }"
    class="swiper-testimonial"
    :centered-slides="true"
    direction="horizontal"
    :loop="true"
    :autoplay="{ delay: 3e3 }"
    :modules="[Pagination]"
  >
    <swiper-slide v-for="item, idx in testimonialData" :key="idx">
      <div class="testimonial">
        <div class="testimonial-body">
          <div class="card">
            <div class="card-body">
              <div class="d-flex pb-3">
                <div class="p-0 pe-3">
                  <img
                    :src="item.imgUrl"
                    class="img-thumbnail"
                    height="60px"
                    width="60px"
                    loading="lazy"
                  />
                </div>
                <div class="p-0 pe-3 d-flex flex-column justify-content-center">
                  <h5 class="m-0">{{ item.name }}</h5>
                  <h6>
                    <small>{{ item.address }}</small>
                  </h6>
                </div>
                <div class="p-0 pe-3 d-flex align-items-center flex-grow-1 justify-content-end">
                  <img
                    src="assets/img/yelp-logo.webp"
                    class="img-fluid"
                    height="41px"
                    width="82px"
                    loading="lazy"
                  />
                </div>
              </div>
              <div class="row stars pb-3">
                <img
                  src="assets/img/stars.webp"
                  class="review-stars"
                  height="18px"
                  width="99px"
                  loading="lazy"
                />
              </div>
              <div class="row content">
                <p>
                  <small>{{ item.content }}</small>
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>