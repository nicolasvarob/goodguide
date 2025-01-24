<script lang="ts">
  import Icon from "@iconify/svelte";
  import dummy_items from "../lib/dummy_items.json";


  let ITEMS =  dummy_items;

</script>

<div
  class="previewer-viewport p-4 md:p-10 space-y-4 "
>
  <div
    class="previewer-preview flex justify-center items-center mx-auto transition-[width] duration-200 w-full"
  >
    <div class="w-full text-token grid grid-cols-1 lg:grid-cols-5 md:grid-cols-2 gap-4">
      {#each ITEMS as item (item.id)}
        <a
          class="card !bg-transparent card-hover overflow-hidden"
          href="/product/{item.id}"
          ><header>
            <img
              src={item.preview_img}
              class="bg-black/50 w-full aspect-[13/9]"
              alt="Post"
            />
          </header>
          <div class="p-4 h-40 space-y-2">
            <h6 class="h6" data-toc-ignore="">{item.activity_category?.toUpperCase()}</h6>
            <h3 class="h3" data-toc-ignore="">{item.title}</h3>
          </div>
          <div class="p-4 h-15">
            <p class="flex items-center"><Icon style="color:  #FF5533" icon="ic:baseline-fmd-good" />&nbsp; Pucon</p>
          </div>
          <div class="p-4 h-15">
            <p class="flex items-center">{item.activity_length}</p>
          </div>
        </a>
      {/each}
    </div>
  </div>
</div>
