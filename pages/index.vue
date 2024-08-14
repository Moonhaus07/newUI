<template>
  <div class="bg-gray-900 text-white">
    <header class="py-4 px-6 flex justify-between items-center">
      <div>
        <img src="../img/Lending_logo.png" alt="LendCash Logo" class="object-cover h-16 w-12" />
      </div>
      <nav>
        <ul class="flex space-x-6 text-sm">
          <li><a href="/" class="hover:underline">Home</a></li>
          <li><a href="/offer" class="hover:underline">Offer</a></li>
          <li><a href="/about" class="hover:underline">About</a></li>
          <li><a href="/subscription" class="hover:underline">Subscription</a></li>
          <li>
            <button
              :class="slideIndex === 0 ? 'bg-black text-white' : 'bg-white text-black'"
              class="font-bold py-1 px-3 rounded flex items-center text-sm"
            >
              Apply Here
              <i class="fas fa-mouse-pointer ml-2"></i>
            </button>
          </li>
        </ul>
      </nav>
    </header>
    <section
      v-if="slideIndex === 0"
      class="bg-cover bg-center bg-no-repeat py-16 text-center"
      style="background-image: url('../img/firstbg_handshake.jg'); background-color: rgba(0, 0, 0, 0.6); background-blend-mode: darken;"
    >
      <h1 class="text-3xl font-bold mb-4" style="color: #6FFC2D;">ERD Financial Solution</h1>
      <h2 class="text-xl mb-2 text-white">An Online Microfinance Lending System</h2>
      <h3 class="text-2xl font-bold mb-8" style="color: #6FFC2D;">Creating Opportunities, One Microloan at a Time</h3>
      <div class="mt-8">
        <button @click="nextSlide" class="bg-gray-700 text-white px-4 py-2 rounded mr-2">Next</button>
      </div>
    </section>

    <section v-if="slideIndex === 1" class="bg-gray-900 text-white py-16">
      <div class="container mx-auto px-4 text-left">
        <h2 class="text-2xl font-extrabold mb-8" style="color: #6FFC2D;">LendCash Microfinance System for ERD Financial Solutions</h2>
        <img src="" alt="Related Image" class="w-1/3 float-right ml-4 mb-4"/>
        <p class="text-base mb-8">Providing financial servicing to people who are not eligible for banking loans and related loan services. This targets individuals and small businesses by offering affordable financial products. Microfinance institutions empower low-income individuals to start or expand businesses, improve their livelihoods, and achieve financial independence.</p>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-8">
          <div class="flex flex-col items-center">
            <img src="" alt="Easy Loan Process" class="h-20 w-20 object-cover mb-4" />
            <h5 class="text-lg font-bold">Easy Loan Process</h5>
            <p>Text about Easy Loan Process.</p>
          </div>
          <div class="flex flex-col items-center">
            <img src="" alt="Quick Cash Disbursement" class="h-20 w-20 object-cover mb-4" />
            <h5 class="text-lg font-bold">Quick Cash Disbursement</h5>
            <p>Text about Quick Cash Disbursement.</p>
          </div>
          <div class="flex flex-col items-center">
            <img src="" alt="Hassle Free Requirements" class="h-20 w-20 object-cover mb-4" />
            <h5 class="text-lg font-bold">Hassle-Free Requirements</h5>
            <p>Text about Hassle-Free Requirements.</p>
          </div>
        </div>
        <div class="mt-8">
          <button @click="prevSlide" class="bg-gray-700 text-white px-4 py-2 rounded mr-2">Back</button>
          <button @click="nextSlide" class="bg-gray-700 text-white px-4 py-2 rounded">Next</button>
        </div>
      </div>
    </section>

    <footer class="bg-white py-2 px-4 text-center" style="color: #090A15;">
      <p class="text-sm">&copy; 2023 LendCash. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slideIndex: 0,
    };
  },
  methods: {
    nextSlide() {
      this.slideIndex = (this.slideIndex + 1) % 2;
    },
    prevSlide() {
      this.slideIndex = (this.slideIndex - 1 + 2) % 2; // ensure it stays within bounds
    },
  },
};
</script>

<style scoped>
.bg-cover {
  background-size: cover;
  background-position: center;
}
</style>