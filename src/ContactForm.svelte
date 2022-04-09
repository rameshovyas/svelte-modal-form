<script>
import { createEventDispatcher } from 'svelte';

 let dispatch = createEventDispatcher();
 let name;
 let email;
 //let emailSupport=false;
 //let productEnquiry = true;
 //let somethingElse = false;
 let medium="Email";
 let reasons = [];
 const handleSubmit = () => {
    const contact = {
        name, 
        email, 
        medium, 
        reasons
    };

    //Custom event dispatching
    //first argument 'addContact' is the name of function
    //second argument is the data we want to send along
    dispatch('addContact',contact);


 }
</script>

<form on:submit|preventDefault={handleSubmit}>
 <input type="text" placeholder="Your Name" bind:value={name}/>
 <input type="text" placeholder="Your Email" bind:value={email}/>
 <label>Suitable Medium to contact back<br>
 <select bind:value={medium}>
     <option value="Email">Email</option>
     <option value="Phone">Phone</option>        
 </select>   

 <label>What are you looking for?<br>
 <!--<input type="checkbox" bind:checked={emailSupport}>Email Support<br>
 <input type="checkbox" bind:checked={productEnquiry}>Product Enquiry<br>
 <input type="checkbox" bind:checked={somethingElse}>Something else<br>
 -->
 <input type="checkbox" bind:group={reasons} value="emailSupport">Email Support<br>
 <input type="checkbox" bind:group={reasons} value="productEnquiry">Product Enquiry<br>
 <input type="checkbox" bind:group={reasons} value="somethingElse">Something else<br>
 <button>Submit</button>
</form>


<style>

</style>