<template>
    <div class="flex items-center justify-center h-screen">
      <div class="bg-white p-8 rounded-md shadow-md relative w-[300px]">
        <button class="i-mdi-close absolute top-3 right-3 text-gray-500 hover:text-gray-700 focus:outline-none"></button>
        <h1 class="text-2xl font-bold text-center mb-4">How many stars would you give to them ?</h1>
        <p class="text-gray-700 text-center pb-6">Jonah Noah delivered your order from <span class="font-bold">Nanica Homemade Pies</span>, today at 19:47 (7 min ahead schedule).</p>
        <ul class="text-center">
          <li @mouseover="hoverStar(1)" @mouseleave="leaveStar()" :class="starClass(1)"></li>
          <li @mouseover="hoverStar(2)" @mouseleave="leaveStar()" :class="starClass(2)"></li>
          <li @mouseover="hoverStar(3)" @mouseleave="leaveStar()" :class="starClass(3)"></li>
          <li @mouseover="hoverStar(4)" @mouseleave="leaveStar()" :class="starClass(4)"></li>
          <li @mouseover="hoverStar(5)" @mouseleave="leaveStar()" :class="starClass(5)"></li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        stars: 0
      };
    },
    methods: {
      hoverStar(starCount) {
        this.stars = starCount;
      },
      leaveStar() {
        this.stars = 0;
      },
      starClass(starNumber) {
        return {
          'i-mdi-star': this.stars >= starNumber,
          'i-mdi-star-outline': this.stars < starNumber,
          'text-yellow-500': this.stars >= starNumber,
          'text-purple-500': this.stars < starNumber,
          'text-4xl': true,
        };
      }
    }
  };
  </script>
  