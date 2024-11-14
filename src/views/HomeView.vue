<script setup>

import { ref } from 'vue';

const welcome1 = ref(true);
const welcome2 = ref(false);
const cantik = ref(0);
const qeustion = ref(false);
const ngejekAudy = ref(false);
const audyCantik = ref(false);
const jawabanEnggak = ref(false);

function btnCantik() {
  cantik.value++;
  console.log(cantik.value);

  if (cantik.value >= 1) {
    qeustion.value = false;
    ngejekAudy.value = true;
  }

  if (cantik.value >= 2) {
    qeustion.value = false;
    ngejekAudy.value = false;
    audyCantik.value = true;
  }
}

function btnEnggak() {
  jawabanEnggak.value = true;
  qeustion.value = false;
  ngejekAudy.value = false;
  audyCantik.value = false;
}

function btnUlangQuestion() {
  qeustion.value = true;
  ngejekAudy.value = false;
  audyCantik.value = false;
  jawabanEnggak.value = false;
}

function btnNext1() {
  welcome1.value = false;
  welcome2.value = true;
}

function btnNext2() {
  welcome2.value = false;
  qeustion.value = true;
}
</script>

<template>


  <main class="h-screen relative overflow-hidden">
    <video autoplay muted loop class="absolute -z-10 top-0 left-0 w-full h-full object-cover">
      <source src="@/assets/video/background.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <div class="absolute z-20 left-0 top-0 w-full h-full bg-black bg-opacity-50 flex items-center justify-center">
      <div class="w-[550px] rounded-3xl bg-opacity-60 bg-white p-8 ">

        <!-- welcome 1-->
        <div v-if="welcome1" class="flex flex-col items-center justify-center">
          <div class="w-[100px] h-[100px] rounded-full overflow-hidden mb-8">
            <img src="@/assets/img/kasihbungalucu.jpeg" alt="">
          </div>
          <div class="">
            <p class="pacifico-regular text-3xl text-slate-900 mb-6">Aloo audrey febriany silalahi</p>
            <p class="dancing-script-700 text-xl text-slate-900 ">aku harus buat nama panggilan sendiri si nnti hehehe 🥰</p>
            <div class="w-full flex justify-around mt-5">
              <button @click="btnNext1" class="px-4 py-2 bg-orange-200 bg-opacity-25 border-2 rounded-md border-orange-300 hover:bg-opacity-60 ease-in duration-300">lanjut >></button>
            </div>
          </div>
        </div>
        <!-- welcome 1-->

        <!-- welcome 2 -->
        <div v-if="welcome2" class="flex flex-col items-center justify-center">
          <div class="w-[100px] h-[100px] rounded-full overflow-hidden mb-8">
            <img src="@/assets/img/kasihbungalucu.jpeg" alt="">
          </div>
          <div class="">
            <p class="pacifico-regular text-2xl text-center text-slate-900 mb-6">sebelumnya,,ini ada beberapa pertanyaan, jawab dulu yaa!</p>
            <div class="w-full flex justify-around mt-5">
              <button @click="btnNext2" class="px-4 py-2 bg-orange-200 bg-opacity-25 border-2 rounded-md border-orange-300 hover:bg-opacity-60 ease-in duration-300">lanjut >></button>
            </div>
          </div>
        </div>
        <!-- welcome 2 -->

        <!-- question audy cantik -->
        <div v-if="qeustion" class="flex flex-col items-center justify-center">
          <div class="w-[100px] h-[100px] rounded-full overflow-hidden mb-8 ">
            <img src="@/assets/img/kasihbungalucu.jpeg" alt="">
          </div>
          <div class="">
            <p class="pacifico-regular text-5xl text-slate-900 mb-6">Apakah audyy cantik?</p>
            <div class="w-full flex justify-around">
                <button
                  class="px-4 py-2 bg-orange-200 bg-opacity-25 border-2 rounded-md border-orange-300 hover:bg-opacity-60 ease-in duration-300"
                  @click="btnCantik"
                >
                  iyaa!
                </button>
              <button @click="btnEnggak" class="px-4 py-2 bg-orange-200 bg-opacity-25 border-2 rounded-md border-orange-300 hover:bg-opacity-60 ease-in duration-300">enggak</button>
            </div>
          </div>
        </div>

        <!-- container ngejek audy -->
        <div v-if="ngejekAudy" class="flex flex-col items-center justify-center">
          <div class="w-[100px] h-[100px] rounded-full overflow-hidden mb-8">
            <img src="@/assets/img/kasihbungalucu.jpeg" alt="">
          </div>
          <div class="">
            <p class="text-center pacifico-regular text-2xl text-slate-900 mb-4">DIH KO PEDE BANGET HAHAHA🤣</p>
            <p class="text-center dancing-script-400 text-2xl">Berchandyaaaa✌️, beneran deh kali ini aku ulang ya pertanyaan nya!</p>
            <div class="flex justify-center mt-2">
              <button @click="btnUlangQuestion" class="px-4 py-2 bg-orange-200 bg-opacity-25 border-2 rounded-md border-orange-300 hover:bg-opacity-60 ease-in duration-300">ulang</button>
            </div>
          </div>
        </div>
        <!-- container ngejek audy -->

        <!-- card kalo audy mencet enggak -->
        <div v-if="jawabanEnggak" class="flex flex-col items-center justify-center">
        <div class="w-[100px] h-[100px] rounded-full overflow-hidden mb-8">
          <img src="@/assets/img/kasihbungalucu.jpeg" alt="">
        </div>
        <div class="">
          <p :class="cantik == 0 ? '' : 'hidden'" class="text-xl text-slate-900 mb-6">Lohh kok gitu sihh, jawab ulangg gaak😤</p>
          <p :class="cantik== 1 ? '' : 'hidden'" class="text-xl text-slate-900">Tadi itu becandhaa loohh, jawab ulangg gaa!</p>
          <div class="flex justify-center mt-2">
              <button @click="btnUlangQuestion" class="px-4 py-2 bg-orange-200 bg-opacity-25 border-2 rounded-md border-orange-300 hover:bg-opacity-60 ease-in duration-300">ulang</button>
            </div>
        </div>
        </div>
        <!-- card kalo audy mencet enggak -->

        <!-- card audy cantik beneran -->
         <div v-if="audyCantik" class="flex flex-col items-center justify-center">
          <div class="w-[100px] h-[100px] rounded-full overflow-hidden mb-8">
            <img src="@/assets/img/kasihbungalucu.jpeg" alt="">
          </div>
          <div class="">
            <p class="text-center dancing-script-400 text-2xl text-slate-900 ">Iyaa audyy itu cantik bingiitttt tauu, tuh bukti fotonyaa cantik bangett</p>
            <div class="flex justify-center mt-2">
              <RouterLink to="/bunga" class="px-4 py-2 bg-orange-200 bg-opacity-25 border-2 rounded-md border-orange-300 hover:bg-opacity-60 ease-in duration-300">Ini ada sesuatu buat kamu</RouterLink>
            </div>
          </div>
         </div>
        <!-- card audy cantik beneran -->


        <!-- question audy cantik -->

      </div>

    </div>
  </main>


</template>

<style scoped>

</style>
