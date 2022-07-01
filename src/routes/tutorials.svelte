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
         tutorials {
            title
            url
            category
         }
      }
    `;

    const { tutorials } = await graphcms.request(query)

    return {
      props: {
        tutorials,
      },
    }
  }

</script>

<script>
   export let tutorials;
   console.log({ tutorials })
   const sortedTutorials = tutorials.sort((a,b) => a?.category.trim().toLowerCase() > b?.category.trim().toLowerCase() ? 1 : -1);
   import TutorialCard from '../components/cards/tutorialcard.svelte';
</script>

<head>
  <title>
</head>
<ul role="list" class="divide-y divide-gray-200">
  {#each sortedTutorials as tutorial}
   <TutorialCard
      title={tutorial?.title}
      category={tutorial?.category}
      url={tutorial?.url}
   /> 
  {/each}
</ul>



