<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-container-logo" @click="greet">
        <img src="~/assets/images/logo.png" alt="logo" />
      </div>
      <div class="navbar-container-buttons">
        <ul class="navbar-container-buttons-actions">
          <li>
            <router-link to="/">home</router-link>
          </li>
          <li>
            <router-link to="/products">products</router-link>
          </li>
          <li>
            <router-link to="/products">on sale</router-link>
          </li>
          <li>
            <router-link to="/products">newsroom</router-link>
          </li>
          <li>
            <router-link to="/products">contact us</router-link>
          </li>
        </ul>
        <div class="navbar-container-buttons-divider"></div>
        <div class="cart">
          <span class="material-icons">{{ setIcon }}</span>
        </div>
        <div class="navbar-container-buttons-divider"></div>
        <ul class="navbar-container-buttons-actions">
          <li><router-link to="/login">login</router-link></li>
          <li class="navbar-container-buttons-actions__button">
            <router-link to="/login">register</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator'

interface Fluggen {
  name: string
  surname: string
}

@Component
export default class Navbar extends Vue {
  @Prop({ type: Object }) readonly fluggen!: Fluggen

  greet(e: any): void {
    console.log(e.target)
  }

  get setFluggen(): string {
    return `${this.fluggen.name} ${this.fluggen.surname}`
  }

  get setIcon(): any {
    return 'shopping_cart'
  }
}
</script>


<style lang="scss" scoped>
h1 {
  color: white;
}
.navbar {
  background: $color-black-1;
  widows: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

  &-container {
    width: 80%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 0;

    &-logo {
      color: $color-white;
    }

    &-buttons {
      display: flex;
      justify-content: space-evenly;
      align-items: center;

      &-actions {
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        list-style: none;
        text-decoration: none;
        margin: 0;
        padding: 0;

        li {
          margin: 0 10px;
          padding: 0;
          text-transform: uppercase;
          font-size: 12px;
        }

        &__button {
          background: $color-beige;
          border-radius: 30px;
          padding: 5px 10px !important;
        }
      }

      &-divider {
        background: $color-dark-grey;
        height: 20px;
        width: 1px;
        margin: 0 10px;
      }
    }
  }

  .cart {
    color: $color-white;
  }
}
</style>