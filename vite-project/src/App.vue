<template>
  <div>
    <div class="container">
      <input type="text" v-model="searchQuery" @input="search" placeholder="Qidiruv">
      <ul>
        <li v-for="result in searchResults" :key="result.id">
          <img :src="result.image" alt="">
          {{ result.name }}
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      searchQuery: '',
      data: [
        { id: 1, name: 'Nodirbek', image: '../src/assets/user-img/Nodirbek.jpg' },
        { id: 2, name: 'Ibrohim', image: '../src/assets/user-img/Ibroxim.jpg' },
        { id: 3, name: 'Sardorbek', image: '../src/assets/user-img/Sardorbek.jpg' },
        { id: 4, name: 'Akbar', image: '../src/assets/user-img/Akbarali.jpg' },
        { id: 5, name: 'Jobirhon', image: '../src/assets/user-img/Jobirxon.jpg' },        
        { id: 6, name: 'Asadbek', image: '../src/assets/user-img/Asadbek.jpg' },
        { id: 7, name: 'Diyorbek', image: '../src/assets/user-img/Diyorbek.jpg' },
        { id: 8, name: 'Suhrobjon', image: '../src/assets/user-img/Suhrobjon.jpg' }
      ],

    };
  },
  computed: {
    searchResults() {
      return this.data.filter(item =>
        item.name.toLowerCase().includes(this.searchQuery.toLowerCase())
      );
    }
  },
  methods: {
    search() {
      // Optional: Make an API call to search
    }
  }
}
</script>
<style scoped>
.container {
  padding: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-image: url('file:///C:/Users/user/Downloads/Fluid@1x-10.0s-1536px-730px.svg');
}

@media (max-width: 1440px) {
  .container{
    width: 100% !important;
    border: 1px solid red;
  }
  ul{
    gap: 0;
  }
}

.container input {
  width: 40%;
  height: 35px;
  border-radius: 5px;
  outline-style: none;
  border: 0.5px solid black;
  padding: 10px;
}

ul {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  gap: 35px;
  margin-top: 45px;
}

ul:hover li:not(:hover) {
  opacity: .7;
  transform: scale(.85);
  transition: all 0.5s cubic-bezier(0.23, 1, 0.58, 0.37);
}

ul li {
  clip-path: polygon(20% 0%, 80% 0%, 100% 20%, 100% 100%, 80% 100%, 20% 100%, 0 100%, 0% 20%);
  border: 1px solid black;
  width: 280px;
  height: auto;
  list-style: none;
  padding: 15px;
  text-align: center;
  margin: 0;

  img {
    width: 100%;
    object-fit: cover;
    height: 280px;
  }
}
</style>