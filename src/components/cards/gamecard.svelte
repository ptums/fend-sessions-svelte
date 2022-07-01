<script>
  export let url;
  export let types;
  export let title;

  import { generateLabelColors } from "../../utils/helper.ts";
</script>

<li class="block hover:bg-gray-50">
    <div class="px-4 py-4 sm:px-6">
       <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between">
          <p class="mb-2 text-base font-medium text-indigo-600 truncate sm:mb-0">{title}</p>
          <div class="flex flex-shrink-0 sm:ml-2">
            <p class={`inline-flex px-2 text-xs font-semibold ${generateLabelColors(types)} rounded-full leading-5`}>
                 {types}
             </p>
           </div>
        </div>
        <div class="mt-2 sm:flex sm:justify-between">
           <div class="sm:flex">
              <p class="flex flex-row items-center h-5 text-sm text-gray-500">
                  <a href={url} class="mr-2 underline" rel="noopener noreferrer nofollow">
                    {url}  
                  </a>
              </p>                   
           </div>
           
        </div>
      </div>
  </li>
