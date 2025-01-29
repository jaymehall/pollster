<script>
    import {createEventDispatcher} from "svelte";
    const dispatch = createEventDispatcher();
    import Button from "../shared/Button.svelte";

    let fields = {question: "", answerA: "", answerB: ""}
    let errors = {...fields};
    const fieldRequiredMsg = "You must fill out this field";
    let isValid = false;
    const submitHandler = () => {
        isValid = true;
        // validate question
        if(fields.question.trim().length < 5) {
            isValid = false;
            errors.question = "Question must be at least 5 characters long"
        } else {
            errors.question = "";
        }

        //validate answerA
        if(fields.answerA.trim().length === 0) {
            isValid = false;
            errors.answerA = fieldRequiredMsg;
        } else {
            errors.answerA = "";
        }

        //validate answerB
        if(fields.answerB.trim().length === 0) {
            isValid = false;
            errors.answerB = fieldRequiredMsg;
        } else {
            errors.answerB = "";
        }
       if(!isValid) return;

       const poll = {...fields, votesA: 0, votesB: 0, id: Math.random()};
       dispatch("add", poll);
    }
</script>

<form on:submit|preventDefault={submitHandler}>
    <div class="form-field">
        <label for="question">Poll Question:</label>
        <input type="text" id="question" bind:value={fields.question}/>
        <div class="error">{errors.question}</div>
    </div>
    <div class="form-field">
        <label for="answer-a">Answer A:</label>
        <input type="text" id="question" bind:value={fields.answerA}/>
        <div class="error">{errors.answerA}</div>
    </div>
    <div class="form-field">
        <label for="answer-b">Answer B:</label>
        <input type="text" id="question" bind:value={fields.answerB}/>
        <div class="error">{errors.answerB}</div>
    </div>
    <Button type="primary" flat={true} inverse={true}>Add Poll</Button>
</form>

<style>
    form {
        width: 400px;
        margin: 0 auto;
        text-align: center;
    }
    .form-field{
        margin: 18px auto;
    }
    input{
        width: 100%;
        border-radius: 6px;
    }
    label{
        margin: 10px auto;
        text-align: left;
    }
    .error{
        color: red;
        font-size: small;
        text-align: left;
    }
</style>