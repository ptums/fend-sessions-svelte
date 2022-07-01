<script context="module">
   import { gql, GraphQLClient } from 'graphql-request'
   
   export async function load() {
      const url = "https://api-us-east-1.graphcms.com/v2/cl43i3zwv5dty01xjaab6hf3j/master";
 
    const graphcms = new GraphQLClient(
      url, 
      {
        headers: {},
      }
    )

    const query = gql`
      query {
         sessions {
            title
            completed
            solution {
               url
            }
            lessonActivity {
               url
            }
            closeDate
            types
         }
      }
    `;

    const { sessions } = await graphcms.request(query)

    return {
      props: {
        sessions,
      },
    }
  }

</script>

<script>
   export let sessions;
   const sortedSessions = sessions.sort((a, b) => new Date(a?.closeDate) > new Date(b?.closeDate) ? 1 : -1 ); 
   import SessionCard from '../components/cards/sessioncard.svelte';
</script>

<head>
  <title>
</head>
<ul role="list" class="divide-y divide-gray-200">
  {#each sortedSessions as session}
   <SessionCard
    completed={session?.completed}
    types={session?.types}
    lessonActivity={session?.lessonActivity}
    solution={session?.solution}
    closeDate={session?.closeDate}
    title={session?.title}
  /> 
  {/each}
</ul>



