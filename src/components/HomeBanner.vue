<template>
		<!-- Home Banner -->
			<section class="section-search">
				<div class="container">
					<div class="banner-wrapper">
						<div class="banner-header">
							<p>We specialize in Pediatric Care</p>
							<h1>A SAFE CARE FOR YOUR CHILDREN’s HEALTH</h1>
							<p class="small-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna Quis ipsumpsum.</p>
							<router-link to="/doctor/search" class="btn-pink">Make Appointment <i class="fas fa-arrow-right"></i></router-link>
						</div>						
					</div>
				</div>
			</section>
			<!-- /Home Banner -->
</template>

<script>
export default {
	mounted() {
		if($('.pharmacy-home-slider .swiper-container').length > 0) {
		 	var swiper = new Swiper('.pharmacy-home-slider .swiper-container', {
		 	loop: true,
		 	speed: 1000,
	      	pagination: {
	        	el: '.pharmacy-home-slider .swiper-pagination',
	        	dynamicBullets: true,
	        	clickable: true,
	      	},
	      	navigation: {
        		nextEl: '.pharmacy-home-slider .swiper-button-next',
        		prevEl: '.pharmacy-home-slider .swiper-button-prev',
      		},
	    });
	}
	},
	computed: {
		currentpath() {
			return this.$route.name;
		}
	},
	 methods: {
		searchPath() {
			this.$router.push('/doctor/search')
		}
    },
}
</script>