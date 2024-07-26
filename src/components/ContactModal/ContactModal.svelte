<script lang="ts">

	import InformationModal from '../InformationModal/InformationModal.svelte';
	import PhoneIcon from '../Icon/PhoneIcon.svelte';

	export let display: boolean = false;
	let email: string = 'nicolasdevos.45@gmail.com';
	let linkedin: string = 'https://www.linkedin.com/in/nicolas-devos-897505192/';
	let phone: string = '+33781322809';

</script>

<InformationModal bind:display>
	<div slot="title">
		<h2>Contact</h2>
	</div>
	<div slot="content">
		<div id="content">

		<span id="mailTo">
					<span class="icon">
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
					</span>
				<a href="mailto:{email}">{email}</a>
		</span>
		<span id="linkedin">
			<span class="icon">
				<img src="LinkedIn.png" alt="linkedin" width="25px">
			</span>
			<a href="{linkedin}">Linkedin</a>
		</span>
		<span id="phone">
			<span class="icon">
			<PhoneIcon width="25px" style="fill: #ccc" stroke="#777"></PhoneIcon>
			</span>
			<a href="tel:{phone}">{phone}</a>
		</span>
		</div>


	</div>
</InformationModal>

<style lang="scss">
  h2 {
    margin: 5px;
    font-size: 1.2em;
		font-weight: 500;
		color: var(--color-secondary);
  }


  div#content {
    display: grid;
    gap: 10px;

    span.icon {
      background: #eee;
      border-radius: 50%;
      padding: 10px;

    }

    span, a {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;
      gap: 10px;
    }

    a {
      color: var(--color-tertiary);
    }
  }
</style>