<script lang="ts">
  import {
    ListBox,
    ListBoxItem,
    popup,
    type PopupSettings,
  } from "@skeletonlabs/skeleton";
  import dayjs from "dayjs";
  import "dayjs/locale/ar";
  dayjs.locale("ar");

  let Period = dayjs().format("a") == "م" ? "مساء" : "صباح";
  let comboboxValue: string = "جميع المهام";

  const popupCombobox: PopupSettings = {
    event: "click",
    target: "popupCombobox",
    placement: "bottom",
    closeQuery: ".listbox-item",
  };
</script>

<header class="flex justify-between">
  <div>
    <h1 class="text-4xl text-pink-900 mb-2">{Period} الخير 👋</h1>
    <h2 class="text-2xl text-pink-900/50">
      {dayjs().format("اليوم dddd  D MMM YYYY ")}
    </h2>
  </div>

  <button
    class="bg-pink-900/30 active:bg-pink-900/10 w-28 h-14 h-fit rounded-full py-4 btn variant-filled w-48 justify-between"
    use:popup={popupCombobox}
  >
    <span > {comboboxValue}</span>
    <span class="!m-0">
      <svg class="w-6 text-pink-900 "
        xmlns="http://www.w3.org/2000/svg"
      
        viewBox="0 0 24 24"
      >
        <path d="M0 0h24v24H0z" fill="none" />
        <path
          fill="none"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="m5 12l7 7l7-7m-7 7V5"
        />
      </svg>
    </span>
  </button>

  <div class="card w-48 shadow-xl py-2" data-popup="popupCombobox">
    <ListBox rounded="rounded-none">
      <ListBoxItem class="text-rose-950 hover:bg-pink-800/50" bind:group={comboboxValue} name="medium" value="جميع المهام"
        >جميع المهام</ListBoxItem
      >
      <ListBoxItem class="text-rose-950 hover:bg-pink-800/50" bind:group={comboboxValue} name="medium" value="مهام اليوم"
        >مهام اليوم</ListBoxItem
      >
      
      
    </ListBox>
    <div class="arrow bg-surface-100-800-token" />
  </div>
</header>
