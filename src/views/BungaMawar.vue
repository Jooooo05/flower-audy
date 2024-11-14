<script setup>
import { onMounted, ref } from "vue";

const audio = ref(null);

</script>

<template>
  <main>
    <div class="h-screen flex justify-center items-center bg-animation flower-container">
      <!-- SVG Bunga Utama dengan animasi tumbuh -->
      <svg
        width="300"
        height="700"
        viewBox="0 0 200 400"
        xmlns="http://www.w3.org/2000/svg"
        class="bloom-animation"
      >
        <!-- Batang Bunga -->
        <line x1="100" y1="180" x2="100" y2="350" stroke="#3b7a57" stroke-width="4" />

        <!-- Daun -->
        <ellipse cx="80" cy="260" rx="20" ry="10" fill="#3b7a57" />
        <ellipse cx="120" cy="280" rx="20" ry="10" fill="#3b7a57" />

        <!-- Kelopak Bunga -->
        <circle cx="100" cy="150" r="30" fill="pink" />
        <circle cx="130" cy="170" r="30" fill="pink" />
        <circle cx="70" cy="170" r="30" fill="pink" />
        <circle cx="73" cy="120" r="30" fill="pink" />
        <circle cx="130" cy="120" r="30" fill="pink" />

        <!-- Tengah Bunga -->
        <circle cx="100" cy="150" r="15" fill="yellow" />
      </svg>

      <!-- audio -->
      <div class="hidden">
        <audio
        hidden="true"
        ref="audio"
        autoplay>
          <source src="@/assets/video/you_are_enough.mp3" type="audio/mpeg">
        </audio>
      </div>
      <!-- audio -->

      <!-- surat buat audy -->
      <div class="w-4/5 m-auto">

        <h1 class="pacifico-regular text-2xl">To : Audrey Febriany Silalahi🥰</h1>

        <p class="mt-6 text-xl">Hallo lagi audyy👋, satu hal yang ga aku nyangka banget, bisa tau dan bisa kenal kamu,,tiba2 di telfon sama ellen dia bilang mau kenalin temennya ke aku hahah, terus pas aku liat fotonya aku lsg mikir dalam hati hhmmm "kayaknya ni orang sombong dehh wkwkwk" cuma pas udah kenal orangnya, mikir lagi dalam hati "eh ni orang asik bet dah, positif banget lagi orangnya" wah jadi semangat gini kan buat dapetin wkwkwk 😋, cuma pas uda makin kenal sempet ragu, keknya sikap dia ke semua orang sama aja dehh wkwkwk, cuma pas dijelasin kek okeey🤗 hehehe, Aku ngerasa kayak bersyukurr banget deh bisa kenal kamu, semoga kamu juga ngerasa hal yang sama ya ke aku.</p>
        <p class="mt-3 text-xl">Audyy kamu udah suka belom cara aku ngetreat kamu? jujur aja aku masih banyak kekurangan, jadi kasih aku cara ngetreat yang terbaik menurut kamu ya, soalnya pasti semua orang pengen di treat dengan cara yang berbeda-beda. jadi kalo misalnya ada apa - apa bilang aja yaa,,kalo misalnyaa ada sikap aku yang ga kamu suka atau sikap aku yg nyakitin kasih tau aja. aku harap kita bisa saling mengerti satu sama lain, bisa saling support satu sama lain, bisa saling menghibur satu sama lain, semuaanya dehh pokoknya 🥰</p>

        <p class="mt-5 text-xl pacifico-regular">LOVE YOU 100%</p>

        <h3 class="mt-8 text-3xl pacifico-regular text-center">YOU ARE ENOUGH</h3>


      </div>
      <!-- surat buat audy -->
    </div>



  </main>
</template>

<style scoped>
/* Animasi utama bunga mekar */
.bloom-animation {
  transform-origin: center bottom;
  animation: bloom 2s ease-out forwards;
}

@keyframes bloom {
  0% {
    transform: scale(0) translateY(100%);
    opacity: 0;
  }
  50% {
    transform: scale(1.1) translateY(0);
    opacity: 1;
  }
  100% {
    transform: scale(1) translateY(0);
    opacity: 1;
  }
}

/* Container animasi latar */
.flower-container {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}



@keyframes float-1 {
  0% {
    transform: scale(0) translate(0, 0);
    opacity: 0;
  }
  50% {
    transform: scale(1.5) translate(-30px, -30px);
    opacity: 1;
  }
  100% {
    transform: scale(0) translate(-60px, -60px);
    opacity: 0;
  }
}

@keyframes float-2 {
  0% {
    transform: scale(0) translate(0, 0);
    opacity: 0;
  }
  50% {
    transform: scale(1.5) translate(30px, -30px);
    opacity: 1;
  }
  100% {
    transform: scale(0) translate(60px, -60px);
    opacity: 0;
  }
}

@keyframes float-3 {
  0% {
    transform: scale(0) translate(0, 0);
    opacity: 0;
  }
  50% {
    transform: scale(1.5) translate(-30px, 30px);
    opacity: 1;
  }
  100% {
    transform: scale(0) translate(-60px, 60px);
    opacity: 0;
  }
}

@keyframes float-4 {
  0% {
    transform: scale(0) translate(0, 0);
    opacity: 0;
  }
  50% {
    transform: scale(1.5) translate(30px, 30px);
    opacity: 1;
  }
  100% {
    transform: scale(0) translate(60px, 60px);
    opacity: 0;
  }
}

/* Animasi background gradient */
.bg-animation {
  background: linear-gradient(45deg, #f1f7ff, #ffe4e1, #f7f1ff, #e1ffe1);
  background-size: 400% 400%;
  animation: gradientShift 10s ease-in-out infinite;
}

@keyframes gradientShift {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>
