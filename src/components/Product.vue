<template>
  <div class="container">
    <div class="left-column"><img v-bind:src="product.image"></div>
    <div class="right-column">
      <div class="product-description">
        <p>{{ product.category }}</p>
        <h4>{{ product.title }}</h4>
        <p>{{ product.description }}</p>
      </div>
      <div class="product-rating">
        <p>Rating</p>
        <p>{{ product.rating.rate}} based on {{product.rating.count}} voters</p>
      </div>
      <div class="product-price">
        <p>{{ product.price }}$</p><a class="cart-btn" href="#">Add to cart</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product",
  props: {
    products: Object
  },
  data: function () {
    return {
      product: this.products
    }
  }
}
</script>

<style scoped>
html, body {
  height: 100%;
  width: 100%;
  margin: 0;
  font-family: 'Roboto', sans-serif;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 15px;
  display: flex;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 5px;
}
.container:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.left-column {
  width: 55%;
  position: relative;
}

.right-column {
  width: 45%;
  margin-top: 60px;
  text-align: left;
}

.left-column img {
  width: 50%;
  margin-top: 200px;
}

.product-description {
  border-bottom: 1px solid #E1E8EE;
  margin-bottom: 20px;
}

.product-description span {
  font-size: 12px;
  color: #358ED7;
  letter-spacing: 1px;
  text-transform: uppercase;
  text-decoration: none;
}

.product-description h4 {
  font-weight: 300;
  font-size: 52px;
  color: #43484D;
  letter-spacing: -2px;
}

.product-description p {
  font-size: 16px;
  font-weight: 300;
  color: #86939E;
  line-height: 24px;
}

.product-rating {
  font-size: 16px;
  font-weight: 300;
  color: #86939E;
  line-height: 24px;
}

.product-price {
  display: flex;
  align-items: center;
}

.product-price span {
  font-size: 26px;
  font-weight: 300;
  color: #43474D;
  margin-right: 20px;
}

.cart-btn {
  display: inline-block;
  background-color: #7DC855;
  border-radius: 6px;
  font-size: 16px;
  color: #FFFFFF;
  text-decoration: none;
  padding: 12px 30px;
  margin: 30px;
  transition: all .5s;
}

.cart-btn:hover {
  background-color: #64af3d;
}

@media (max-width: 940px) {
  .container {
    flex-direction: column;
    margin-top: 60px;
  }

  .left-column,
  .right-column {
    width: 100%;
  }

  .left-column img {
    width: 300px;
    right: 0;
    top: -65px;
    left: initial;
  }
}

@media (max-width: 535px) {
  .left-column img {
    width: 220px;
    top: -85px;
  }
}

</style>