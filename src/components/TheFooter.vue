<template>
	<footer class="footer">
		<div class="container">
			<div class="footer-newsletter">
				<input
					type="text"
					id="newsletter"
					aria-label="Sign up for newsletter"
					placeholder="Sign up and get updates"
				/>
				<button class="btn">Go</button>
			</div>

			<div class="footer-navigation">
				<div class="footer-main-links spacing-sm">
					<a href="#home" class="footer-link">Home</a>
					<a href="#pricing" class="footer-link">Pricing</a>
					<a href="#product" class="footer-link">Product</a>

					<a href="#about" class="footer-link"> About Us</a>
				</div>
				<div class="footer-sec-links spacing-sm">
					<a href="#careers" class="footer-link"> Careers</a>
					<a href="#community" class="footer-link"> Community</a>
					<a href="#community" class="footer-link"> Privacy policy</a>
				</div>
			</div>
			<div class="footer-brands">
				<div class="footer-social">
					<a href="#" class="social-link">
						<img
							class="social-icon"
							src="@/assets/images/icon-facebook.svg"
							alt=""
						/>
					</a>
					<a href="#" class="social-link">
						<img
							class="social-icon"
							src="@/assets/images/icon-youtube.svg"
							alt=""
						/>
					</a>
					<a href="#" class="social-link">
						<img
							class="social-icon"
							src="@/assets/images/icon-instagram.svg"
							alt=""
						/>
					</a>
					<a href="#" class="social-link">
						<img
							class="social-icon"
							src="@/assets/images/icon-twitter.svg"
							alt=""
						/>
					</a>
					<a href="#" class="social-link">
						<img
							class="social-icon"
							src="@/assets/images/icon-pinterest.svg"
							alt=""
						/>
					</a>
				</div>
				<a class="footer-logo" href="#">
					<img src="@/assets/images/logoWhite.svg" alt="" />
				</a>
			</div>
			<div class="footer-copyright">
				Copyright 2020. All Rights Reserved
			</div>
		</div>
	</footer>
</template>


<style lang="scss" scoped>
@import "@/assets/sass/_variables";

.footer {
	background-color: var(--blue-600);
	padding: 5em 0;
}
.container {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;

	@media only screen and(min-width:$v-12) {
		flex-direction: row;
		justify-content: space-between;
		align-items: flex-start;
	}

	& > * + * {
		margin-top: 7.5rem;
		@media only screen and(min-width:$v-12) {
			margin-top: 0;
		}
	}
}
.footer-newsletter {
	@media only screen and(min-width:$v-12) {
		order: 4;
	}
	display: flex;
	align-items: center;
	input {
		border-radius: 5rem;
		padding: 0.7em 1em;
		border-radius: 5rem;
		margin-right: 1.5rem;
	}
	.btn {
		text-transform: uppercase;
	}
	.btn:focus {
		outline: 1px solid var(--grey);
	}
}

.footer-navigation {
	@media only screen and(min-width:$v-12) {
		order: 2;
	}
	width: 100%;
	max-width: 30rem;
	display: flex;
	justify-content: space-between;
	.footer-main-links {
		display: flex;
		flex-direction: column;
	}
	.footer-sec-links {
		display: flex;
		flex-direction: column;
	}
	.footer-link {
		font-size: 1.8rem;
		color: var(--grey);
	}
	.footer-link:hover,
	.footer-link:focus {
		color: var(--accent);
	}
}

.footer-brands {
	@media only screen and(min-width:$v-12) {
		order: 1;

		display: flex;
		height: 100%;
		flex-direction: column-reverse;
		justify-content: space-between;
	}
	& > * + * {
		margin-top: 6rem;
		@media only screen and(min-width:$v-12) {
			margin-top: 0;
		}
	}
	.footer-social {
		display: flex;
		align-items: center;

		& > * + * {
			margin-left: 2.5rem;
		}
		.social-link {
			.social-icon {
				width: 3.5rem;
			}
		}
		.social-link:focus {
			outline: 1px solid var(--grey);
		}
	}
	.footer-logo {
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 0.5rem 0;
		@media only screen and(min-width:$v-12) {
			margin-bottom: 10rem;
		}
	}
	.footer-logo:focus {
		outline: 1px solid var(--grey);
	}
}

.footer-copyright {
	color: var(--blue-300);
	@media only screen and(min-width:$v-12) {
		position: absolute;
		right: 0;
		bottom: 0;
	}
}
</style>