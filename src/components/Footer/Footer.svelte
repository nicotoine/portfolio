<script lang="ts">
	import { base } from '$app/paths';

	let email: string = 'nicolasdevos.45@gmail.com';
</script>

<footer>
	<div class="footer">
		<div class="footer__content">
			<div class="footer__content__left">
				<div class="footer__content__left__title">
					<h2>Me contacter</h2>
				</div>
				<div class="footer__content__left__contact">
					<div class="footer__content__left__contact__item">
							<svg width="25" height="25" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
								<g clip-path="url(#clip0_108_33)">
									<path
										d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22H17V20H12C7.66 20 4 16.34 4 12C4 7.66 7.66 4 12 4C16.34 4 20 7.66 20 12V13.43C20 14.22 19.29 15 18.5 15C17.71 15 17 14.22 17 13.43V12C17 9.24 14.76 7 12 7C9.24 7 7 9.24 7 12C7 14.76 9.24 17 12 17C13.38 17 14.64 16.44 15.54 15.53C16.19 16.42 17.31 17 18.5 17C20.47 17 22 15.4 22 13.43V12C22 6.48 17.52 2 12 2ZM12 15C10.34 15 9 13.66 9 12C9 10.34 10.34 9 12 9C13.66 9 15 10.34 15 12C15 13.66 13.66 15 12 15Z"
										fill="#bbb" />
								</g>
								<defs>
									<clipPath id="clip0_108_33">
										<rect width="24" height="24" fill="white" />
									</clipPath>
								</defs>
							</svg>
						<p>
							<a href="mailto:{email}">{email}</a>
						</p>
					</div>
				</div>

			</div>
			<div class="footer__content__right">
				<div class="footer__content__right__title">
					<h2>Liens</h2>
				</div>
				<div class="footer__content__right__links">
					<a href="https://www.linkedin.com/in/nicolas-devos-897505192/">
						<img src="{base}/LinkedIn.png" alt="linkedin" width="25px">
						Linkedin
					</a>
					<a href="https://github.com/nicotoine">
						<img src="{base}/github.png" alt="linkedin" width="25px">
						Github
					</a>
				</div>
			</div>
		</div>
	</div>

	<div class="footer__bottom">
		<p>© Nicolas Devos 2024</p>
	</div>


</footer>

<style lang="scss">
  @import '../../../static/variables';

  footer {
    background:  var(--color-primary);
    color: white;
    padding: 20px 0;
		position: relative;
		bottom: 0;
		margin-top: 20px;
  }

  .footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .footer__content {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    width: 100%;
  }

  .footer__content__left {
    display: flex;
    flex-direction: column;
  }

  .footer__content__left__title {
    margin-bottom: 10px;
  }

  .footer__content__left__contact {
    display: flex;
    flex-direction: column;
  }

  .footer__content__left__contact__item {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
		gap: 10px;
  }

  .footer__content__right {
    display: flex;
    flex-direction: column;
  }

  .footer__content__right__title {
    margin-bottom: 10px;
  }

  .footer__content__right__links {
    display: flex;
    flex-direction: column;
  }

  .footer__bottom {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
  }

  .footer__bottom p {
    margin: 0;
  }

  .footer__content__left__contact__item img {
    width: 20px;
    height: 20px;
    margin-right: 10px;
  }

	.footer__content__right__links img {
		width: 20px;
		filter: grayscale(100%);
  }
	.footer__content__right__links:hover  img{
		filter: grayscale(0%);
  }
  .footer__content__right__links a {
    margin-bottom: 10px;
		gap: 10px;
  }

  .footer__content__right__links a:hover {
    text-decoration: underline;
  }

  .footer__content__right__links a {
    color: white;
		display: flex;
		align-items: center;
		gap: 10px;
  }

  .footer__content__right__links a:hover {
    color: var(--color-primary);
  }

  .footer__content__left__contact__item p {
    margin: 0;
  }

  .footer__content__left__contact__item a {
    color: white;
  }

  .footer__content__left__contact__item a:hover {
    color: var(--color-primary);
  }

  .footer__content__left__contact__item a {
    text-decoration: none;
  }

  .footer__content__left__contact__item a:hover {
    text-decoration: underline;
  }

  .footer__content__left__contact__item a {
    color: white;
  }


</style>
