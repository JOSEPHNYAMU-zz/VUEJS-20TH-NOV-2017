<template>
    <div class="hello home">
        <router-link id="lin" to="/">Home</router-link>
        <router-link style="background-color: #cccccc;" id="lin" to="/Profile">Profile</router-link>
        <br/><br/>
        <fieldset class="fie">
            <legend><h2>TO DO LIST</h2></legend>
            <div id="inputs">
                <form v-on:submit.prevent='addTodo'>
                    <input class="inp" required v-model="newTodo" type="text" placeholder="Add a Task"/>
                    <button type="submit" class="btn">ADD A TASK</button>
                </form>
                <br><br><br>

                <table width="100%">
                    <tr style="border-bottom: solid 1px #cccccc;" class="full" v-for="todo in todos">
                        <td style="width:200px">
                            <input class="chk" type="checkbox" v-model="todo.completed"/>
                        </td>
                        <td style="width:350px;text-align: left;">
                            <span :class="{completed: todo.completed}">{{ todo.name }}</span>
                        </td>
                        <td style="width:150px;text-align:right;">
                            <button type="submit" class="del" v-on:click.prevent="deleteTodo(todo)">Delete</button>
                        </td>
                    </tr>
                </table>
                <ul type="none">

                    <li><span id="count">{{ remaining }} Complete Task(s)</span></li>
                </ul>

                <ul type="none">
                    <input class="chk" type="checkbox"/>
                </ul>
            </div>
        </fieldset>

    </div>
</template>

<script>
  export default {
    name: 'Profile',
    data () {
      return {
        msg: 'Hello Profile'
      }
    }
  }
</script>
