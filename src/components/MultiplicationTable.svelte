<!-- MultiplicationTable.svelte -->
<script>
    let selectedNumber = 1;
    const multipliers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12];

    function handleNumberChange(e) {
        selectedNumber = parseInt(e.target.value, 10);
    }
</script>

<div class="container">
    <div class="box">
    <h1 class="multiplication-header">Multiplication Table 🚀</h1>
    <div class="input-container">
        <label for="number" class="input-label">Enter a number:</label>
        <input
        type="number"
        id="number"
        bind:value={selectedNumber}
        class="input-field"
        on:input={handleNumberChange}
        />
    </div>
    <div>
        <table class="table">
        <thead class="table-header">
            <tr>
            <th class="table-header">Multiplication</th>
            <th class="table-header">Result</th>
            </tr>
        </thead>
        <tbody>
            {#each multipliers as multiplier (multiplier)}
            <tr key={multiplier}>
                <td class="table-cell center">{selectedNumber} * {multiplier}</td>
                <td class="table-cell center">{selectedNumber * multiplier}</td>
            </tr>
            {/each}
        </tbody>
        </table>
    </div>
    </div>
</div>

<style>
td {
    background-color: #f5f5f5;
}

.box {
    background-color: #f5f5f5;
    padding: 30px;
}

.center {
    text-align: center;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 0.25rem;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
    padding: 1rem;
    background: linear-gradient(
    45deg,
    #FF0000,
    #FFA500,
    #FFFF00,
    #008000,
    #0000FF,
    #4B0082,
    #8B00FF
    );
    background-size: 200% 200%;
    animation: rainbowBackground 10s linear infinite;
}

@keyframes rainbowBackground {
    0% {
    background-position: 0 100%;
    }
    100% {
    background-position: 100% 0;
    }
}

.multiplication-header {
    font-size: 2rem;
    font-weight: bold;
    margin-bottom: 1rem;
}

.input-container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
}

.input-label {
    font-size: 1rem;
    margin-right: 1rem;
}

.input-field {
    border: 2px solid #ccc;
    border-radius: 0.25rem;
    padding: 0.5rem;
    font-size: 1rem;
}

.table {
    width: 100%;
    border-collapse: collapse;
    padding: 50px;
}

.table-header {
    padding: 0.5rem 1rem;
    background-color: #eee;
}

.table-cell {
    padding: 0.5rem 1rem;
    border-bottom: 1px solid #ccc;
    font-size: 1rem;
}

.table-cell:nth-child(even) {
    background-color: #f5f5f5;
}

</style>
