<template>
	<!-- Doctor Section -->
	<section class="section doctor-section">
		<div class="container">
			<div class="section-header">
				<h6>Meet our Professionals</h6>
				<h2>Our Doctors <router-link to="/doctor/search" class="member-btn">View all members</router-link> </h2>	
			</div>
			<div class="row justify-content-center">
				<div class="col-md-6 col-lg-3" v-for="item in doctors" :key="item.id">
					<div class="profile-card">
						<div class="profile-image">
							<router-link to="/doctor/index">
								<img :src="loadImg(item.image)" alt="">
							</router-link>
						</div>
						<div class="profile-content">
							<h3><router-link to="/doctor/index">{{item.name}}</router-link></h3>
							<p>{{item.specialist}}</p>
							<div class="social-icon">
								<ul>
									<li>
										<a href="#" target="_blank"><i class="fab fa-facebook-f"></i> </a>
									</li>
									<li>
										<a href="#" target="_blank"><i class="fab fa-youtube"></i></a>
									</li>
									<li>
										<a href="#" target="_blank"><i class="fab fa-twitter"></i> </a>
									</li>
								</ul>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>
	<!-- /Doctor Section -->
</template>

<script>
const images = require.context('@/assets/img/doctors', false, /\.png$|\.jpg$/)
import doctors from '../assets/json/doctors'

export default {
    data() {
        return {
			doctors: doctors,
			slickOptions: {
                slidesToShow: 4,
                arrows:true,
                dots: false,
				swipeToSlide: true,
				variableWidth: true,
                responsive: [
                {
                    breakpoint: 1024,
                    settings: {
                        slidesToShow: 3,
                        slidesToScroll: 3,
                    }
                },
                {
                    breakpoint: 600,
                    settings: {
                        slidesToShow: 2,
                        slidesToScroll: 2
                    }
                },
                {
                    breakpoint: 480,
                    settings: {
                        slidesToShow: 1,
                        slidesToScroll: 1
                    }
                }
                ]
            },
        };
	},
	methods: {
        loadImg(imgPath) {
		   return images('./' + imgPath)
        },
    },
}
</script>