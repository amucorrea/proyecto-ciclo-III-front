<template>
 <div id="CrearCompranpm">
   <div>
     <h1>Agregar Compra</h1>
     <form id="form" v-on:submit.prevent="procesar">
        <p> Id Compra: <input type="numb" name="id_compra" placeholder="Id_Compra" class="form-comtrol" v-model= "compras.id_compra"> </p>
        <p> Cedula: <input type="numb" name="cedula" placeholder="cedula" class="form-comtrol" v-model= "compras.cedula"></p>
        <p>Nombre_Producto: <input type="text" name="Nombre_Producto" placeholder="Nombre_Producto" class="form-comtrol" v-model= "compras.Nombre_producto"></p>
        <p>Cantidad: <input type="numb" name="Cantidad" placeholder="Cantidad" class="form-comtrol" v-model= "compras.cantidad"></p>
        <p>Precio: <input type="numb" name="Precio" placeholder="Precio" class="form-comtrol" v-model= "compras.Precio"></p>
        <p>Total: <input type="numb" name="Total" placeholder="Total" class="form-comtrol" v-model= "compras.Total"></p>
        <hr>
        <input type="submit" value="">
     </form>
    </div>
    <table class="table">
          <thead>
              <tr>
                 <th> id_compra</th>
                 <th> Cedula</th>
                 <th> nombre_producto</th>
                 <th> cantidad</th>
                 <th> precio</th>
                 <th> Total</th>
               </tr> 
            </thead>
          </table>
        <tbody>
            
             <tr>
               <td>{{d.id_compra}}</td>
               <td>{{d.cedula}}</td>
               <td>{{d.nombre_producto}}</td>
               <td>{{d.cantidad}}</td>
               <td>{{d.precio}}</td>
               <td>{{d.Total}}</td>
             </tr>
        </tbody>    
    </div> 
</template>

<script>
  import Vue from 'vue';
  import axios from 'axios';

  export default { 
    name: "CrearCompranpm",    
    data : function(){ 
      return {
            compras_in: {
            id_compra:"",
            cedula:"",
            nombre_producto:"",
            cantidad:"",
            precio: "",
            Total:"",
            },
          }
    },
  methods: {
    guardarCompra(){
      this.form.token = localStorage.getItem("token");
            axios.post("https://minisap01.herokuapp.com/clientes/compras/"+this.data)
            .then(data =>{
                console.log(data);
                this.makeToast("Hecho","cliente creado","success");
            }).catch( e =>{
                console.log(e);
                 this.makeToast("Error","Error al guardar","error");
            })
    },
  addExpense(e) { 
      e.preventDefault();
      const input = document.querySelector('#input').value;
      if(input.trim() === 'none'){return alert('¡Usted debe llenar todos lo campos!')};
      {
        procesar() 
          {
            const  name_form= form     
          }
      }
    }
  }
 }
</script>