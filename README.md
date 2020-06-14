# to-do-list-vue
 
https://pamavoc-todolist-vue.netlify.app/


Quick to-do-list made in VueJS 

STRUCTURE OF THE APP

- We have a Header.vue component, a Tache.vue (Task) component, a Contenu.vue (content) component and of course our main component : App.vue
- Contenu.vue & Header.vue are the children of App.vue
- Tache.vue is the child of Contenu.vue

HOW IT WORKS

- Our component 'Contenue.vue' has a structure made with a <template>, a <script>, and a <style> tag.
- Contenue.vue loads Tache.vue so they can "communicate" together with the props.
- In the template of Contenue.vue, we can find the form with a button which allows us to create a task 
- This button and this form are linked to the script part of our component.
- In the <script> tag we have methods (functions) they allow us to create/delete a task when we type inside of our input/when we click on the red cross of our Tache.vue component
- When the task is created, she is pushed inside an array
- The suppression (delete) function use the method splice to remove an element from the array
- Both methods are trigger through buttons. In our <template> we bind the method with a v-on:click=""
- To display the task, we linked our array with a v-for loop on the <li> so we can iterate on it. Each time a new value is added inside our input, it will be added to the arraw and then, displayed in a <li>.
- To delete, a button is trigger on Tache.vue. This button take a v-on:click="suppression". "suppression" is a props sent to the parent, so the method is recognized when we click on the button
 - In Contenue.vue, we have a v-bind:suppression="suppression" to link the props of Tache.vue to Component.vue so when we click on the redcross, the task is suppressed.
 
THAT'S ALL ;)
