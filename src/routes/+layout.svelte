<script lang="ts">
  import { inject } from "@vercel/analytics";
  import "../app.css";

  let { children } = $props();

  // Initialize analytics
  inject();
</script>

{@render children()}
