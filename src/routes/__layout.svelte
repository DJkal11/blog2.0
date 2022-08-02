<script>
	import '../app.css';
</script>



<nav class="bg-white sticky top-0 border-gray-200 px-2 sm:px-4 py-2.5 dark:bg-gray-900">
	<div class="container flex flex-wrap justify-between items-center mx-auto">
	  <a href="/" class="flex items-center">
		  <span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">Blogged</span>
	  </a>
	  
	  <div class=" w-full sm:w-full sm:block  md:w-auto" id="navbar-default">
		<ul class="flex flex-row p-4 mt-4 rounded-lg  md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:border-0 sm:flex-row  dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
		  <li>
			<a href="/" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent" aria-current="page">Home</a>
		  </li>
		  <li>
			<a href="/About" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">About</a>
		  </li>
		  <li>
			<a href="/blogs" class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Blogs</a>
		  </li>
		</ul>
	  </div>
	</div>
  </nav>

<main>
	
	<slot />
</main>

<footer class=" fixed bottom-0  w-screen p-4 bg-white shadow md:flex md:items-center md:justify-between md:p-6 dark:bg-gray-800">
    <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400">© 2022 <a href="" class="hover:underline">Friend A Labs</a>. All Rights Reserved.
    </span>
</footer>


<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
