<script>
   const person = {
     imageUrl: "https://www.tumulty.dev/_next/image?url=%2Fimages%2Fpeter-face.webp&w=384&q=75",
     name: "Peter Tumulty",
     role: "Senior Frontend Engineer",
     twitterUrl:"https://twitter.com/ptums923",
     linkedinUrl:"https://www.linkedin.com/in/petertumulty",
     githubUrl: "https://github.com/ptums",
     email: "ptumulty923@gmail.com"
   }
   import FaTwitter from 'svelte-icons/fa/FaTwitter.svelte'
   import FaLinkedin from 'svelte-icons/fa/FaLinkedin.svelte'
   import FaGithubSquare from 'svelte-icons/fa/FaGithubSquare.svelte'
</script>

<div class="max-w-xl px-6 py-10 mx-auto text-center xl:px-10 xl:text-left">
      <img class="w-40 h-40 mx-auto rounded-full xl:h-48 xl:w-48" src={person.imageUrl} alt={person?.name} />
      <div class="mt-6 xl:flex xl:items-center xl:justify-between">
        <div class="text-lg font-medium leading-6 space-y-1">
          <h3 class="text-white">{person.name}</h3>
          <p class="text-indigo-400">{person.role}</p>
          <p class="text-indigo-400">{person.email}</p>
        </div>
        <ul role="list" class="flex justify-center">
          <li>
            <a href={person.twitterUrl} class="text-gray-400 block mr-2 h-6 w-6 hover:text-gray-300" target="_blank">
              <span class="sr-only">Twitter</span>
              <FaTwitter/> 
            </a>
         </li>
         <li>
           <a href={person.linkedinUrl} class="text-gray-400 block mr-2 h-6 w-6 hover:text-gray-300" target="_blank">
             <span class="sr-only">LinkedIn</span>
             <FaLinkedin /> 
           </a>
         </li>
         <li>
           <a href={person.githubUrl} class="text-gray-400 block w-6 h-6 hover:text-gray-300" target="_blank">
             <span class="sr-only">Github</span>
             <FaGithubSquare />
           </a>
         </li>
       </ul>
     </div>
 </div>

