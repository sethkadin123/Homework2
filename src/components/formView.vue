<template>
  <div>
    <h1>List of Fruits</h1>
    <div class="main-card">
      <div class="card" v-for="fruit in fruits" :key="fruit.name">
        <div class="card-header">
          <h3>{{ fruit.name }}</h3>
          <img :src="fruit.Image" :alt="fruit.name">
        </div>
        <div class="card-body">
          <button>{{ fruit.quantity }}</button>
          <p>{{ fruit.description }}</p>
          <!-- <button @click="fruit.quantity++">+</button> -->
          <button type="button" class="btn btn-success">Add New</button>
          <button type="button" class="btn btn-danger" @click="deleteFruit(fruit)">Delete</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fruits: [
        {
          Image: "https://i.pinimg.com/736x/52/08/b0/5208b0e909679fb39313e644b59483d9.jpg",
          quantity: "10$",
          description: "Rich in vitamin c",
          name: "orange",
        },
        {
          Image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR-iuY_8CHb5GJl3oPw53m8bUhvd_Zi97FPC_vPdJQpvrC1yYD4QnMlGbKpPZcpFm6pty4&usqp=CAU",
          quantity: "15$",
          description: "Pomegranate is much better",
          name: "Pomegranate",
        },
      ]
    };
  },
  methods: {
    deleteFruit(fruit) {
      const index = this.fruits.indexOf(fruit);
      if (index !== -1) {
        this.fruits.splice(index, 1);
      }
    }
  }
};
</script>

<style scoped>
h1 {
  text-align: center;
  margin-top: 30px;
  font-size: 30px;
  font-weight: bold;
  color: #4caf50;
}

.main-card {
  display: flex;
  gap: 10px;
  margin-top: 30px;
  justify-content: center;
}

img {
  width: 100%;
}

.card {
  width: 23%;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 10px;
  border-radius: 10px;
}

button {
  border: none;
  border-radius: 20px;
  padding: 10px;
  background-color: #4caf50;
  color: white;
  cursor: pointer;
}

.card-body {
  padding: 10px;
  background-color: rgb(212, 204, 204);
}
</style>
