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
         games {
            title
            url
            types
         }
      }
    `;

    const { games } = await graphcms.request(query)

    return {
      props: {
        games
      },
    }
  }

</script>

<script>
   export let games;
   const sortedGames = games.sort((a, b) => a?.types.trim().toLowerCase() > b?.types.trim().toLowerCase() ? 1 : -1);
   import GameCard from '../components/cards/gamecard.svelte';
</script>

<head>
  <title>
</head>
<ul role="list" class="divide-y divide-gray-200">
  {#each sortedGames as game}
   <GameCard
      title={game?.title}
      types={game?.types}
      url={game?.url}
   /> 
  {/each}
</ul>



