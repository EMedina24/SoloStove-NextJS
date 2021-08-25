<template>


<header class="text-gray-600 body-font">
    <div class="banners" data-banner-location="top">
		<div class="banner">
			<p>
				Get exclusive offers, free gear, and points on every order! <a class="ss-rewards-banner" title="Create an account, Get exclusive offers, free gear, and points on every order!" href="/login.php">Get your rewards</a>.
			</p>
		</div>
	</div>
  <div class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center">
   
      <img  class="header-logo-image " src="https://cdn11.bigcommerce.com/s-b5b4c/stencil/062223a0-e415-0139-f667-62078a6417ff/e/62407500-9406-0139-90d3-56a0962d5e72/img/ss-logo-registered-2021.svg">
   
    <nav class="md:mr-auto md:ml-4 md:py-1 md:pl-4 	flex flex-wrap items-center text-base justify-center">
      <a href="https://www.solostove.com/" class="desktop-header-nav-item-label">Fire Pits</a>
      <a  href="https://www.solostove.com/" class="desktop-header-nav-item-label">Grill</a>
      <a  href="https://www.solostove.com/" class="desktop-header-nav-item-label">Camp Stoves</a>
      <a  href="https://www.solostove.com/" class="desktop-header-nav-item-label">Apparel</a>
      <a href="https://www.solostove.com/"  class="desktop-header-nav-item-label">Corporate Sales</a>
    </nav>
 
  </div>
</header>
</template>


<style scoped >
.header-logo-image {
    display: block;
    width: 125px;
    height: auto;
    margin: 0 auto;
}

.desktop-header-nav-item-label {
    display: block;
    overflow: hidden;
   
    color: #000;

    padding: 23px 20px 19px;
    font-size: 18px;

    font-weight: 500;
    transition-property: color;
    transition-duration: .2s;
    text-decoration: none;
    position: relative;
    cursor: pointer;
}


.desktop-header-nav-item-label::after {
    content: '';
    width: 18px;
    height: 23px;
    background-image: url(https://cdn11.bigcommerce.com/s-b5b4c/stencil/062223a0-e415-0139-f667-62078a6417ff/e/62407500-9406-0139-90d3-56a0962d5e72/img/solo-stove-flame-only-2x.png);
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center top;
    position: absolute;
    bottom: 0;
    left: 50%;
    -ms-transform: translateX(-50%) translateY(100%);
    transform: translateX(-50%) translateY(100%);
    opacity: 0;
    transition: all .2s;
}

.desktop-header-nav-item-label.is-open::after, .desktop-header-nav-item-label:hover::after, .desktop-header-nav-item-label[aria-expanded=true]::after {
    opacity: 1;
    -ms-transform: translateX(-50%) translateY(0);
    transform: translateX(-50%) translateY(0);
}

.banners {
    background-color: #528ead;
    color: #fff;
    padding: 10px 0 8px;
    text-align: center;
    font-family: Neutra!important;
    font-weight: 600;
}
</style>



<script>
export default {
  data() {
    return {
      isOpen: false
    };
  },
  methods: {
    drawer() {
      this.isOpen = !this.isOpen;
    }
  },
  watch: {
    isOpen: {
      immediate: true,
      handler(isOpen) {
        if (process.client) {
          if (isOpen) document.body.style.setProperty("overflow", "hidden");
          else document.body.style.removeProperty("overflow");
        }
      }
    }
  },
  mounted() {
    document.addEventListener("keydown", e => {
      if (e.keyCode == 27 && this.isOpen) this.isOpen = false;
    });
  }
};
</script>