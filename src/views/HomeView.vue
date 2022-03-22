<template>
  <label
    for="email"
    class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300"
    >Your email</label
  >
  <input
    type="email"
    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
    placeholder="name@gmail.com"
  />

 
  

    <input type="date" value="Date" :min="new Date().toISOString().substr(0, 10)" />

  <button
    @click="checkDate"
    type="button"
    class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
  >
    Submit
  </button>
  <button
    @click="TDate"
    type="button"
    class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
  >
    Date Today
  </button>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      presentDate: "",

    };
  },
  mounted() {
    this.currentDate();
  },
  methods: {
      
    currentDate() {
      document.querySelector('input[type="date"]').valueAsDate = new Date();
      const todayDate = document.querySelector('input[type="date"]');
      this.presentDate = todayDate.value;
    
    },
    TDate() {
      alert(this.presentDate);
    },
    checkDate() {
      const dateSelected = document.querySelector('input[type="date"]');
      var date1 = this.presentDate;
      var date2 = dateSelected.value;

      if (date1 > date2) {
        alert("Date selected is in the Past");
      } else if (date2 > date1) {
        alert("Date Acceptable");
      } else if (date2 == date1) {
        alert("Warning, date selected is today");
      } else {
        alert("error");
      }
    },
  },
};
</script>
