<template>
  <div class="home">
    <div class="container mx-auto px-32">
      <div class="grid sm:grid-cols-2 gap-4 flex items-center home__content">
        <div>
          <p class="text-4xl font-bold tracking-wider">
            Hai, Saya
            <span class="font-black font-black" title="Tommy Alhamra">
              ImotD
            </span>
          </p>
          <div class="py-8 tracking-wide">
            salam kenal 👋, saya suka buat sesuatu. <br />
            mimpi saya menjadi frontend developer <br />
            yang dapat diandalkan. <span class="text-gray-300">~itu saja</span>
          </div>
          <div class="text-gray-500">
            <p>
              <span v-for="m in menus[0].up" :key="m.id">
                <router-link
                  class="hover:text-black tolink"
                  :to="m.link"
                  :title="m.note"
                >
                  {{ m.title }}
                </router-link>
                &#8728;
              </span>
            </p>
            <p>
              <span v-for="g in menus[1].down" :key="g.id">
                <router-link
                  class="hover:text-black tolink"
                  :title="g.note"
                  :to="g.link"
                >
                  {{ g.title }}
                </router-link>
                &#8728;
              </span>
            </p>
          </div>
          <div class="flex text-gray-500 pt-4 w-24 justify-between">
            <a
              class="hover:text-black"
              target="_blank"
              href="https://github.com/imotD"
            >
              <ph-github-logo :size="22" />
            </a>
            <a
              class="hover:text-black"
              target="_blank"
              href="mailto:tommy.alhamra@gmail.com"
            >
              <ph-envelope-simple :size="22" />
            </a>
            <a
              class="hover:text-black"
              target="_blank"
              href="https://id.linkedin.com/in/tommy-alhamra-217112151"
            >
              <ph-linkedin-logo :size="22" />
            </a>
          </div>
        </div>
        <div class="m-auto">
          <img
            src="@/assets/mask-logo.png"
            alt="Dottom Logo"
            title="Branding"
          />
        </div>
      </div>
      <Footer />
    </div>
  </div>
</template>

<script>
import Footer from "@/components/Footer.vue";
import { PhEnvelopeSimple, PhLinkedinLogo, PhGithubLogo } from "phosphor-vue";

export default {
  name: "Home",
  components: {
    PhEnvelopeSimple,
    PhLinkedinLogo,
    PhGithubLogo,
    Footer,
  },
  data() {
    return {
      menus: [
        {
          up: [
            {
              id: 1,
              title: "Portofolio",
              link: "/portofolio",
              note: "Project yang saya Buat",
            },
            {
              id: 2,
              title: "Podcast",
              link: "/podcast",
              note: "Mengasah Komunikasi",
            },
            {
              id: 3,
              title: "Karya",
              link: "/karya",
              note: "Gaya Geni",
            },
          ],
        },
        {
          down: [
            {
              id: 4,
              title: "Dukung",
              link: "/dukung",
              note: "Traktir Kopi untuk saya",
            },
            {
              id: 5,
              title: "Tentang",
              link: "/tentang",
              note: "Orang Biasa gak Special pake Telor",
            },
          ],
        },
      ],
    };
  },
};
</script>
