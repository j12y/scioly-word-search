<script lang="ts">

    
// create a 4x4 grid that includes three words from the words array
function createGrid(words: string[]) {
    let grid = [[]];

    // Generate random characters for a 4x4 grid
    for (let i = 0; i < 4; i++) {
        grid[i] = [];
        for (let j = 0; j < 4; j++) {
            grid[i][j] = String.fromCharCode(Math.floor(Math.random() * 26) + 97);
        }
    }

    // Add the words to the grid
    for (let word of words) {
        let wordAdded = false;
        while (!wordAdded) {
            let randomRow = Math.floor(Math.random() * 4);
            let randomCol = Math.floor(Math.random() * 4);
            let direction = Math.floor(Math.random() * 8);
            let wordLength = word.length;

            // Check if the word can fit in the grid starting from the random position
            if (canFitWord(grid, randomRow, randomCol, direction, wordLength)) {
                addWordToGrid(grid, randomRow, randomCol, direction, word);
                wordAdded = true;
            }
        }
    }

    return grid;
}

let words = ['cars', 'plane', 'bike'];
let grid = createGrid(words);






</script>

<h1 class="m-8 text-4xl font-bold text-black-300 first-letter:text-5xl uppercase">Science Word Search</h1>


<div class="grid grid-cols-4 gap-4">
    {#each grid as row, i}
        {#each row as cell, j}
            <div class="cell bg-gray-200 p-4 text-center">{cell}</div>
        {/each}
    {/each}
</div>

