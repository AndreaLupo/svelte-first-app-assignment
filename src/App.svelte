<script>
import Second from "./Second.svelte";

  export let courseGoal = '';
  //$:console.log(courseGoal);
  $: shouldHighlight = courseGoal.includes("!");

</script>

<h1>Assignment</h1>

<p>Solve these tasks.</p>

<ol>
  <li>Add an input field that allows users to enter a course goal.</li>
  <li>Output the user input in a h1 tag.</li>
  <li>
    Color the output red (e.g. by adding a class) if it contains at least one exclamation mark.
  </li>
  <li>
    Put the h1 tag + output into a separate component to which you pass the user input
  </li>
</ol>

<div>
  Add a course goal: 

  <input bind:value={courseGoal}/>

</div>

<div>
  Course goal is: <h1 class:reddish={shouldHighlight}>{courseGoal}</h1>
</div>

<Second {courseGoal}/>

<style>
.reddish {
  color: red;
}
</style>