<script>
	let todos = [];
	let todoText = '';
	let todoId = 0;
 
	const addTodo = () => {
        const list  = document.querySelector('#list');
		const newTodo = document.createElement('li');
		const newTodoText = document.createElement('span');
		const newTodoCheckBox = document.createElement('input');
        newTodoText.textContent = todoText;
        newTodo.classList.add(`id${todoId+=1}`)
        newTodo.classList.add('todo')
        newTodoCheckBox.classList.add(`id${todoId+=1}`)
        newTodoCheckBox.type = "checkbox"
		newTodo.append(newTodoText);
		newTodo.append(newTodoCheckBox);
        list?.append(newTodo)
	};
	const removeTodo = () => {};
</script>

<div class="main">
	<div class="box">
		<div class="task-input-box">
			<input type="text" bind:value={todoText} placeholder="write new task here..." required />
			<button on:click={addTodo} class="task-add-btn">+</button>
		</div>
		<div class="task-list-box">
			<h1>Todo's</h1>
			<br />
			<div class="task-list">
				<ul id="list">
					<!--tasks appended here dynamically-->
					
					
				</ul>
			</div>
		</div>
	</div>
</div>

<style>
	* {
		margin: 0%;
		padding: 0%;
	}
	.box {
		width: 500px;
		height: 500px;
	}
	.task-input-box {
		width: 90%;
		padding: 25px;
		background-color: rgba(240, 248, 255, 0.692);
		border-radius: 20px;
		display: flex;
		justify-content: space-between;
	}
	.task-input-box input {
		width: 85%;
		padding: 15px;
		background-color: rgba(240, 248, 255, 0.548);
		border-radius: 20px;
		border: none;
		font-size: 30px;
	}
	.task-add-btn {
		padding: 5px;
		font-size: 30px;
		background-color: rgba(240, 248, 255, 0.692);
		border-radius: 20px;
		border: none;
	}
	.task-add-btn:hover {
		border: 3px solid black;
	}
	.task-list {
		border: 2px solid black;
	}
	.task-list-box h1 {
		font-size: 35px;
		font-family: 'Times New Roman', Times, serif;
		padding: 10px;
	}
    ul{
        list-style: none;
    }
	
	.main {
		margin: 0;
		height: 100vh;
		display: grid;
		place-items: center;
       
	}
</style>
