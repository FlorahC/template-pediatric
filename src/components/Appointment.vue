<template>
  <!-- Book Appointment -->
			<section class="section app-form">
				<div class="container">
					<div class="section-header">
						<h6>Make an appointment</h6>
						<h2>Get the right Pediatician book your doctor</h2>
					</div>
					<div class="row justify-content-center">
						<div class="col-md-6 col-lg-6">
							<div class="form-group">
								<input type="text" class="form-control" placeholder="Your Name">
							</div>
							<div class="form-group">
								<select class="form-control">
									<option>Select Service</option>
									<option>Allergy Testing</option>
								</select>
							</div>
						</div>
						<div class="col-md-6 col-lg-6">
							<div class="form-group">
								<input type="text" class="form-control" placeholder="Time & Date">
							</div>
							<div class="form-group">
								<input type="text" class="form-control" placeholder="Phone Number">
							</div>
						</div>
					</div>
					<div class="row justify-content-center mt-4">
						<router-link to="/doctor/search" class="btn-pink">Make Appointment <i class="fas fa-arrow-right"></i></router-link>
					</div>					
				</div>   
			</section>	 
			<!-- Book Appointment -->
</template>