<script lang="ts">
  import dayjs from "dayjs";
  import "dayjs/locale/ar";
  dayjs.locale("ar");

  let Period = dayjs().format("a") == "م" ? "مساء" : "صباح";
</script>

<div class="p-16">
  <header class="flex justify-between">
    <div>
      <h1 class="text-4xl text-pink-900 mb-2">{Period} الخير 👋</h1>
      <h2 class="text-2xl text-pink-900/50">
        {dayjs().format("اليوم dddd  D MMM YYYY ")}
      </h2>
    </div>

    <div class="bg-pink-900/40 w-28 h-14"></div>
  </header>
</div>
