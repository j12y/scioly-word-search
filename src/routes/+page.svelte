<script lang="ts">

let words = ['cars', 'plane', 'bike'];

let grid = [];
for(let i = 0; i < 4; i++) {
    let row = [];
    for(let j = 0; j < 4; j++) {
        row.push(String.fromCharCode(65 + Math.floor(Math.random() * 26)));
    }
    grid.push(row);
}

</script>

<h1 class="m-8 text-4xl font-bold text-black-300 first-letter:text-5xl uppercase">Science Word Search</h1>


<div class="grid grid-cols-4 gap-4">
    {#each grid as row, i}
        {#each row as cell, j}
            <div class="cell bg-gray-200 p-4 text-center">{cell}</div>
        {/each}
    {/each}
</div>

