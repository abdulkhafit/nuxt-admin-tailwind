<template>
  <div>
    <navbar-component></navbar-component>
    <main>
      <Nuxt/>
    </main>
    <footer-component></footer-component>
  </div>
</template>
<script>
import NavbarComponent from "../components/landings/Navbar";
import FooterComponent from "../components/landings/Footer";
export default {
  name: "landing-page",
  components: {
    NavbarComponent,
    FooterComponent
  }
}
</script>
