<script>
  import ApolloClient from "apollo-boost";
  import { setClient } from "svelte-apollo";

  const client = new ApolloClient({
    uri: "https://api-us-east-1.graphcms.com/v2/cl43i3zwv5dty01xjaab6hf3j/master"
  });
  setClient(client);
</script>

