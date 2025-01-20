<script lang="ts">
    interface Todo {
        id: number;
        title: string;
        completed: boolean;
    }
    let randomNumber = $state<number>(0);
    let started = $state<boolean>(false);
    let todos = $state<Todo[]>([]);
    let addFormValues = $state<{ title: string }>({ title: '' });
    const onClickHandler = () => {
        if (!started){
            started = true;
        }
        randomNumber = Math.floor(Math.random() * 100);
    }
    const onAddTodo = () => {
        todos.push({
            id: todos.length + 1,
            title: addFormValues.title,
            completed: false
        });
        addFormValues.title = '';
    }
</script>

<div>
    <h1>Basic markup</h1>
    <form action="">
        <legend>Todo list</legend>
        <ul>
            {#each todos as {id, title}, index}
                <li>{index + 1}. id:{id} title:{title}</li>
            {:else}
                <li>No todos</li>
            {/each}
        </ul>
        <input type="text" bind:value={addFormValues.title} placeholder="Add a new todo" />
        <button onclick={onAddTodo}>Add todo</button>
    </form>
    {#if started}
        <p>Random number: {randomNumber}</p>    
    {:else}
        <p>Click the button to generate a random number</p>
    {/if}
    <button class="bg-blue-600" onclick={onClickHandler}>Random number</button>
</div>