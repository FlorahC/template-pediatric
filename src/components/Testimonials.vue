<template>
   <!-- Testimonial Section -->
			<section class="doctors-col section app-form">
				<div class="container-fluid">					
					<div class="row justify-content-center">	
						<div class="section-header text-center">
							<h6>Feedback from our patients</h6>							
							<h2>TESTIMONIALS</h2>
						</div>
					</div>
				   <div class="row">
						<div class="col-lg-12">
							<slick class="doctor-slider slider" ref="slick" :options="slickOptions">
								
								<!-- Doctor Widget -->
								<div class="profile-widget" v-for="item in testimonials" :key="item.id">
									<div class="test-content">
										<p>{{item.description}}</p>
									</div>
									<div class="test-image d-flex align-items-center">
										<div class="test-profile">
											<router-link to="/doctor/profile">
												<img class="img-fluid" alt="User Image" :src="loadImg(item.image)">
											</router-link>
										</div>
										<div class="test-users">
											<h3>{{item.name}}</h3>
											<p class="mb-0">{{item.profession}}</p>
										</div>
									</div>								
									<div class="pro-footer text-right">
										<i class="fas fa-quote-left"></i>
									</div>
								</div>
								<!-- /Doctor Widget -->
							</slick>
						</div>
				   </div>
				</div>
			</section>
			<!-- /Testimonial Section -->
</template>

<script>
const images = require.context('@/assets/img/patients', false, /\.png$|\.jpg$/)
import testimonials from '../assets/json/testimonials'
export default {
    data() {
        return {
			testimonials: testimonials,
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
        next() {
            this.$refs.slick.next();
        },
        prev() {
            this.$refs.slick.prev();
        },
        reInit() {
            this.$nextTick(() => {
                this.$refs.slick.reSlick();
            });
		},
		 loadImg(imgPath, value) {
			return images('./' + imgPath)
        },
        
    },
}
</script>