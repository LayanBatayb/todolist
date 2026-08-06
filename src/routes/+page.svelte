<script lang="ts">
  import Header from "$lib/Header.svelte";
  import { tasks } from "$lib/stores/tasks";
    import dayjs from "dayjs";

let title="";
$: console.log(title);
function addTask(){
    tasks.update((currentTasks)=>{
        currentTasks.push({
            title,
            assignedDate:dayjs(),
            isDone:false,

        });
return currentTasks;
    });
    title="";
}
</script>

<div class="p-16">
  <Header />

  <div
    class="rounded-full hover:bg-rose-800/15 input-group input-group-divider flex justify-between -[auto_1fr_auto]"
  >
    <input bind:value={title}  class="flex-1" type="search" placeholder="اضف مهمتك" />
    <button on:click={addTask} class=" bg-rose-900/20">اضافة</button>
  </div>
</div>
