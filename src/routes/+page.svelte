<script lang="ts">
	import { Button, Footer, FooterLinkGroup, FooterLink, Tooltip, Modal, Label, Input, Textarea, GradientButton } from 'flowbite-svelte';
	import { Section } from 'flowbite-svelte-blocks';
	import { CheckCircleOutline } from 'flowbite-svelte-icons'
	import me from '$lib/images/me.jpg';
	import anime from '$lib/animate/bg.mp4'

	let formModal = false;
	let replyModal = false;
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Home" />
</svelte:head>

<div class="relative min-h-screen bg-gray-900 text-white flex flex-col justify-center items-center p-6 overflow-hidden">
	<!-- Background Video -->
	<video autoplay loop muted playsinline class="absolute inset-0 w-full h-full object-cover opacity-50 z-0">
		<source src={anime} type="video/mp4">
		Your browser does not support the video tag.
	</video>

	<div class="container mx-auto p-6 mt-5 mb-5 bg-gray-800 text-gray-300 shadow-2xl rounded-2xl flex flex-col md:flex-row items-center gap-8 relative z-10">
		<div class="opacity-100 w-full text-center md:w-1/2 mb-6 md:mb-0 md:mr-6">
			<img src={me} alt="Zdjęcie" class="rounded-full shadow-lg w-88 h-88 md:w-42 md:h-42 object-cover animate__animated animate__zoomIn animate__delay-1s">
		</div>
		<div class="w-full md:w-1/2 px-10">
			<h1 class="mt-3 pb-5 text-4xl font-extrabold text-center text-indigo-400 animate__animated animate__fadeInLeft">Witaj! Nazywam się Karolina Kuchnia</h1>
			<h2 class="text-3xl font-bold mb-4 text-indigo-300 animate__animated animate__fadeInRight">Kim jestem?</h2>
			<p class="leading-relaxed mb-4 animate__animated animate__fadeInUp">
				Jestem pasjonatem rynku forex i tradingu, z wieloletnim doświadczeniem w tej dziedzinie. Moim celem jest pomaganie innym w osiągnięciu finansowej niezależności oraz rozwijaniu umiejętności inwestycyjnych. Pracuję z osobami, które chcą nauczyć się skutecznego handlu na rynkach finansowych i budować stabilną przyszłość.
			</p>

			<h2 class="text-3xl font-bold mt-6 mb-4 text-indigo-300 animate__animated animate__fadeInRight">Dlaczego warto dołączyć do mojego zespołu?</h2>
			<p class="leading-relaxed mb-4 animate__animated animate__fadeInUp">
				Wspólnie możemy osiągnąć sukces! W moim zespole znajdziesz:
			</p>
			<ul class="list-disc list-inside mb-4 animate__animated animate__fadeInUp">
				<li>Indywidualne wsparcie i mentoring</li>
				<li>Dostęp do sprawdzonych strategii tradingowych</li>
				<li>Materiały edukacyjne i szkolenia dostosowane do Twojego poziomu</li>
				<li>Inspirującą społeczność osób o podobnych celach</li>
			</ul>

			<h2 class="text-3xl font-bold mt-6 mb-4 text-indigo-300 animate__animated animate__fadeInRight">Co oferuję?</h2>
			<p class="leading-relaxed mb-4 animate__animated animate__fadeInUp">
				Każdy nowy członek zespołu otrzymuje:
			</p>
			<ul class="list-disc list-inside mb-4 animate__animated animate__fadeInUp">
				<li>Darmowe konsultacje na start</li>
				<li>Wsparcie w wyborze odpowiedniego brokera</li>
				<li>Pomoc w budowie indywidualnego planu tradingowego</li>
				<li>Regularne spotkania online i wymianę doświadczeń</li>
			</ul>

			<div class="text-center mt-8 animate__animated animate__fadeInUp">
				<GradientButton color="purpleToBlue" pill={true} on:click={() => (formModal = true)} >Dołącz teraz!</GradientButton >
			</div>
			<Section>
				<Footer>
					<FooterLinkGroup ulClass="flex flex-wrap items-center text-sm text-gray-500 dark:text-gray-400 sm:mt-0">
						<FooterLink href="/">
							<svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
								<path fill-rule="evenodd" d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z" clip-rule="evenodd" />
							</svg>
						</FooterLink>
						<Tooltip placement="bottom">Like us on Facebook</Tooltip>
						<FooterLink href="/">
							<svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
								<path d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84" />
							</svg>
							<span class="sr-only">Twitter</span>
						</FooterLink>
						<Tooltip placement="bottom">Like us on Twitter</Tooltip>
					</FooterLinkGroup>
				</Footer>
			</Section>

		</div>
	</div>


	<Modal bind:open={formModal} title="Wyślij zapytanie" size="xs" autoclose={false} class="w-full animate__animated animate__fadeIn animate__delay-.5s">
		<form class="flex flex-col space-y-6" action="#">
			<Label class="space-y-2">
				<span>Email</span>
				<Input type="email" name="email" placeholder="name@company.com" required />
			</Label>
			<Label class="space-y-2">
				<span>Imię</span>
				<Input required />
			</Label>
			<Label class="space-y-2">
				<span>Twoja wiadomość</span>
				<Textarea placeholder="Twoja wiadomość" rows={4} name="message" />
			</Label>
			<GradientButton
				color="purpleToBlue"
				type="submit"
				class="w-full bg-indigo-500 hover:bg-indigo-700"
				on:click={() => (formModal = false, replyModal = true)}>
				Submit
			</GradientButton>
		</form>
	</Modal>


	<Modal bind:open={replyModal} title="Dziękujemy za Twoją wiadomość!!!" size="xs" autoclose={false} class="w-full animate__animated animate__fadeIn animate__delay-.5s">
		<div class="flex flex-col items-center text-center space-y-4">
			<CheckCircleOutline class="text-green-500 w-12 h-12 animate__animated animate__bounceIn" />
			<p>Twoje zapytanie zostało pomyślnie wysłane. Skontaktuję się z Tobą najszybciej, jak to możliwe - zazwyczaj w ciągu 24 godzin.</p>
		  </div>
	</Modal>
</div>