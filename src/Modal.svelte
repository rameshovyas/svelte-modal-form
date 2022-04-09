<script>
    export let showModal = false;
    export let isPromo = false;
   // export let message ="This is a default message";
</script>

{#if showModal}
<!-- Event forwarded here to parent component and self event modifier tells only 
    fire when this backdrop is clicked
-->
<div class="backdrop" class:promo={isPromo} on:click|self> 
  <div class="modal">
   <!--   <slot name="heading"></slot>
      <p>Please fill up the form below, we will contact you soon.</p> -->
      <slot></slot>
  </div>
</div>
{/if}


<style>
.backdrop{
    width:100%;
    height:100%;
    position:fixed;
    background:rgba(0,0,0,0.8);
}

.modal{
    padding:15px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10px auto;
    text-align: center;
    background: #ffffff;
}

.promo .modal {
    background: #69E1C8;
    color:#ffffff;
}
</style>
