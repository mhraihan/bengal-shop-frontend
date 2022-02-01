<template>
  <div>
    <div class="container">
      <div class="flex -mx-4 mb-10">
        <Media
          v-for="(logo, index) in logos"
          :key="index"
          :img="logo.img"
          :title="logo.title"
          :text="logo.text"
        />
      </div>
    </div>
    <div class="bg-gray-100 py-20">
      <div class="container">
        <div class="flex">
          <div class="pr-10 w-3/5">
            <Logo />
            <p class="my-8">
              Lorem ipsum dolor sit amet consectetur, adipisicing elit. Optio
              laborum ipsam placeat qui corporis perspiciatis officiis vitae
              amet, culpa voluptatem odio asperiores numquam vero facilis
              repellat? Mollitia exercitationem quos consectetur?
            </p>
            <div class="flex flex-wrap">
              <a href="/" target="_blank" class="mr-4">
                <img
                  src="~/assets/img/apple.png"
                  loading="lazy"
                  alt="apple logo"
                  srcset=""
                />
              </a>
              <a href="/" target="_blank">
                <img
                  src="~/assets/img/play-store.png"
                  loading="lazy"
                  alt="play store logo"
                  srcset=""
                />
              </a>
            </div>
          </div>
          <FooterMenu title="About Us" :links="links1" />
          <FooterMenu title="Info" :links="links2" />
        </div>
        <div class="flex justify-between pt-20 items-center">
          <div class="social-info min-w-max">
            <Social />
          </div>
          <div class="copyright w-full text-center">
            @2022 Copyright All Right Reserved by Bengal Shop
          </div>
          <div class="payment-logo min-w-max">
            <img
              src="~/assets/img/payment-logo.png"
              loading="lazy"
              alt="payment logo"
              srcset=""
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      logos: [
        {
          img: "customer-support.png",
          title: "24 Customer Support",
          text: "Contact us 24 hours",
        },
        {
          img: "product.png",
          title: "Authentic Products",
          text: "Contact us 24 hours",
        },
        {
          img: "payment.png",
          title: "Secure Payment",
          text: "Contact us 24 hours",
        },
        {
          img: "offers.png",
          title: "Best Prices & Offers",
          text: "Contact us 24 hours",
        },
      ],
      links1: [
        {
          url: "/about",
          title: "About Karte",
        },
        {
          url: "/contact",
          title: "Contact",
        },
        {
          url: "/career",
          title: "Career",
        },
        {
          url: "/terms",
          title: "Terms & Conditions",
        },
        {
          url: "/category",
          title: "Category",
        },
      ],
      links2: [
        {
          url: "/about",
          title: "Information",
        },
        {
          url: "/contact",
          title: "Shipping",
        },
        {
          url: "/career",
          title: "Payment",
        },
        {
          url: "/terms",
          title: "Return",
        },
        {
          url: "/category",
          title: "Blog",
        },
      ],
    };
  },
};
</script>
