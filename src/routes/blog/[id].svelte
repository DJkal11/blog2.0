<script context="module"> 
export const load = async ({params, fetch}) => {
    const id = params.id;
   const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
   const post = await res.json();
   console.log(post);
    return {
        props: {
            post,
        },
    };
}

</script>

<script>
    export let post
</script>

<h1>{post.title}</h1>
<p class="text-xl font-light leading-relaxed mt-6 mb-4 text-gray-800">{post.body}</p>
<div class="flex space-x-2 justify-center">
    <a href="/">
    <button
      type="button"
      data-mdb-ripple="true"
      data-mdb-ripple-color="light"
      class="inline-block px-6 py-2.5 bg-blue-600 text-white font-medium text-xs leading-tight uppercase rounded shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out"
    >Back</button></a>
  </div>