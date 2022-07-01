<script>
  export let completed;
  export let types;
  export let lessonActivity;
  export let solution;
  export let closeDate;
  export let title;

  import FaRegCheckCircle from 'svelte-icons/fa/FaRegCheckCircle.svelte';
  import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'
  import { generateLabelColors, generateLabel } from '../../utils/helper.ts';
  import { format  } from 'date-fns'
</script>
  
<style>
  .check-mark {
    @apply w-12;
    @apply h-12;
    @apply mr-4;
    @apply text-green-400;
  }

  .calendar {
    @apply flex-shrink-0;
    @apply mr-1.5;
    @apply h-5;
    @apply w-5;
    @apply text-gray-400;
  }
</style>
<li class="block hover:bg-gray-50">
    <div class="px-4 py-4 sm:px-6">
      <div class="flex flex-col sm:flex-row sm:items-center">
         <div class="check-mark">
           {#if completed}
             <FaRegCheckCircle />
           {/if}
         </div>
        <div class="flex flex-col w-full">
          <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between">
            <p class="mb-2 text-base font-medium text-indigo-600 truncate sm:mb-0">{title}</p>
            <div class="flex flex-shrink-0 sm:ml-2">
              <p class={`inline-flex px-2 text-xs font-semibold ${generateLabelColors(types)} rounded-full leading-5`}>
                {generateLabel(types)}
              </p>
            </div>
          </div>
          <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between">
            <p class="flex flex-row items-center h-5 mt-3 text-sm text-gray-500 sm:mt-1">
                <strong class="mr-2">Downloads:</strong>
                  <a href={lessonActivity?.url} class="mr-3 underline">
                      Lesson & Activity
                    </a>
                    {#if completed && solution?.url}

                      <a href={solution?.url} class="underline">
                        <strong>SOLUTION</strong>
                      </a>
                    {/if}
              </p>
            <div class="flex items-center mt-4 text-sm text-gray-500 sm:mt-2">
              <div class="calendar">
                  <FaRegCalendarAlt />
              </div>

               <p><time dateTime={closeDate}>{format(new Date(closeDate), 'LLLL dd, yyyy')}</time></p>
                         </div>
          </div>
        </div>
      </div>
    </div>
  </li>
