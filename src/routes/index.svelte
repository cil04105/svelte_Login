<script>
  import FaRegUser from 'svelte-icons/fa/FaRegUser.svelte'
  import FaLock from 'svelte-icons/fa/FaLock.svelte'
  const src = 'https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F1b90dfed-b084-49dd-8c03-b42e30e27e76%2FUntitled.png?table=block&id=bd718ada-a95c-44c0-a4c2-581aff05629e&spaceId=9300b0b5-831f-4b8f-9a3b-94ab6aaef8a4&width=2000&userId=addf45e0-500f-45d5-8e55-e9c1e7708cb6&cache=v2'
  
  let current = "Acount"
  
  let inputValue = {email:'', password: ''}
  let handleInput = e => {
    let { name, value } = e.target;
    inputValue = {...inputValue, [name]: value};   
  }
</script>

<form class="absolute left-2/4 top-2/4 -translate-y-2/4 -translate-x-2/4">
    <h1 class="text-center mb-16 font-bold text-3xl"><img {src} alt="genuioLogo" class="h-13 w-14 inline-block">Genuio</h1>

  <div class="flex mb-3 justify-center"> 
    <span on:click={() => {current="Acount"}} 
      class= "{current === 'Acount' ? 'text-blue-400' : ''}  
      inline-block mb-6 pl-5 pr-5  underline underline-offset-8 cursor-pointer">
      Acount Login
    </span>
    <span on:click={() => {current="Phone"}} 
      class=" {current === 'Phone' ? 'text-blue-400' : ''} 
      inline-block mb-6  pl-5 pr-5  underline underline-offset-8 cursor-pointer">
      Phone Login
    </span>
  </div>

  <div class="w-full">
    <div class="w-5 relative top-8 left-2 text-blue-400"><FaRegUser /></div>
    <input type ="email" name="email" placeholder="Username: admin or user" on:change={handleInput} class="block h-12 w-96 mb-6 rounded p-4 pl-8 border-2">
    <div class="w-5 relative top-8 left-2 text-blue-400"><FaLock /></div>
    <input type="password" name="password" placeholder="password: ant.design" on:change={handleInput} class="block  h-12 w-96 mb-6 rounded p-4 pl-8 border-2">
  </div>

  <div class="text-blue-300 mb-6 text-right text-sm cursor-pointer"><p>Forgot password?</p></div>

  <button type="button" class="w-full rounded p-3 bg-blue-400 text-white">Submit</button> 
    
</form>





