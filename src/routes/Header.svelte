<script lang="ts">
	import { Navbar, NavBrand, NavHamburger, NavLi, NavUl} from "flowbite-svelte";
	import logo from "$lib/images/logo.svg"
	import { page } from '$app/stores';

</script>

<Navbar class="dark:bg-gray-900 py-0">
	<NavBrand href="/">
	  <span class="text-lg font-bold p-5">Learn 2 Trade Pro</span>
	</NavBrand>
	<NavHamburger />
	<NavUl>
	</NavUl>
  </Navbar>