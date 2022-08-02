<script context="module">
	
	
	
</script>

<script> 
	import {isOverlayOpen} from "../stores/OverlayStore";
	import { navigate } from "svelte-routing";

	let title = "";
	let content = "";
	
	function postBlog(event) {
     event.preventDefault();
	 fetch('https://jsonplaceholder.typicode.com/posts', {
     method: 'POST',
     body: JSON.stringify({
     title: title,
     body: content,
     userId: 1,
     }),
     headers: {
    'Content-type': 'application/json; charset=UTF-8',
     },
    })
    .then((response) => response.json())
    .then((json) => console.log(json));
    isOverlayOpen.set(true);
	}

	function closeOverlay() {
		console.log("why");
		isOverlayOpen.set(false);
		console.log($isOverlayOpen);
		navigate("/blogs", { replace: true });	
	}

	
</script>

<svelte:head>
	<title>Home</title>
	<meta name="Blog" content="Blog App" />
</svelte:head>
<main>
	<h1>Create A Blog</h1>

	<form>
	
		<div class="mb-6">
    <label for="default-input" class="block mb-2 text-sm font-medium text-black">Title</label>
    <input bind:value={title} type="text" id="default-input" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
</div>
		<div class="mb-4 w-full bg-gray-50 rounded-lg border border-gray-200 dark:bg-gray-700 dark:border-gray-600">
			
			<div class="py-2 px-4 bg-white rounded-b-lg dark:bg-gray-800">
				<label for="editor" class="sr-only">Publish post</label>
				<textarea bind:value={content} id="editor" rows="8" class="block px-0 w-full text-sm text-gray-800 bg-white border-0 dark:bg-gray-800 focus:ring-0 dark:text-white dark:placeholder-gray-400" placeholder="Write an article..." required></textarea>
			</div>
		</div>
		<button on:click={postBlog} class="inline-flex items-center px-5 py-2.5 text-sm font-medium text-center text-white bg-blue-700 rounded-lg focus:ring-4 focus:ring-blue-200 dark:focus:ring-blue-900 hover:bg-blue-800">
			Publish blog
		</button>
	 </form>
    
     {#if $isOverlayOpen}
	 <div class="overflow-x-hidden overflow-y-auto fixed inset-0 z-50 outline-none focus:outline-none justify-center items-center flex">
		<div class="relative w-auto my-6 mx-auto max-w-3xl">
		  <!--content-->
		  <div class="border-0 rounded-lg shadow-lg relative flex flex-col w-full bg-white outline-none focus:outline-none">
			<!--header-->
			<div class="flex items-start justify-between p-5 border-b border-solid border-blueGray-200 rounded-t">
			  <h3 class="text-3xl font-semibold">
				Post has been saved
			  </h3>
			  
			</div>
			<!--body-->
			
			<!--footer-->
			<div class="flex items-center justify-center p-6 border-t border-solid border-blueGray-200 rounded-b">
			  <a href="/blogs" target="_self"><button on:click={closeOverlay} class="bg-emerald-500 text-white active:bg-emerald-600 font-bold uppercase text-sm px-6 py-3 rounded shadow hover:shadow-lg outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150" type="button">
				Go to Blogs
			  </button></a>
			</div>
		  </div>
		</div>
	  </div>
	  <div class="opacity-25 fixed inset-0 z-40 bg-black"></div>
		
	 {/if}

	 
</main>
<style>
	
</style>
