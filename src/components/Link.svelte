<script lang="ts">
  import { routeToString, route, pushRoute, replaceRoute } from "../route";
  import type { Route } from "../route";

  export let to: Route;
  export let className: string = "";
  export let replace: boolean = false;

  function handleClick() {
    if (replace) {
      replaceRoute(to);
    } else {
      pushRoute(to);
    }
  }
</script>

<a
  class={`${routeToString($route) === routeToString(to) ? 'active' : ''} ${className}`}
  on:click={handleClick}>
  <slot />
</a>
