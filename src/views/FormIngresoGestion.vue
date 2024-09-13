 <template>
    <div class="container">
      <h1 class="text-center mb-4 form-title">Ingreso de Gestión</h1>
      <form @submit.prevent="submitForm">
        
        <div class="form-group row">
          <label for="negocio" class="col-sm-4 col-form-label label-margin">Negocio:</label>
          <div class="col-sm-8 ">
            <input
              type="text"
              id="negocio"
              v-model="formData.negocio"
              class="form-control"
              @input="mostrarReferencia"
              required
            />
          </div>
        </div>
  
        
        <div v-if="negocioReferencia" class="alert alert-info">
          Código de referencia: {{ negocioReferencia }}
        </div>
  
        
        <div class="form-group row">
          <label for="usuario" class="col-sm-4 col-form-label">Usuario:</label>
          <div class="col-sm-8 ">
            <input
              type="text"
              id="usuario"
              v-model="formData.usuario"
              class="form-control"
              required
            />
          </div>
        </div>
  
        
        <div class="form-group row">
          <label for="fecha" class="col-sm-4 col-form-label">Fecha:</label>
          <div class="col-sm-8 box-form-campos">
            <input
              type="date"
              id="fecha"
              v-model="formData.fecha"
              class="form-control"
              required
            />
          </div>
        </div>
  
        
        <div class="form-group row">
          <label for="telefono" class="col-sm-4 col-form-label">Teléfono:</label>
          <div class="col-sm-8">
            <select id="telefono" v-model="formData.telefono" class="form-control">
              <option disabled value="0">Seleccione un número</option>
              <option value="676767676">676767676</option>
              <option value="453353223">453353223</option>
            </select>
          </div>
        </div>

        
        <div class="form-group row">
          <label for="direccion" class="col-sm-4 col-form-label">Dirección:</label>
          <div class="col-sm-8">
            <select id="direccion" v-model="formData.direccion" class="form-control">
              <option disabled value="">Seleccione una dirección</option>
              <option value="Av san martin">Av san martin</option>
              <option value="Barrio las lomas">Barrio las lomas</option>
            </select>
          </div>
        </div>
        
        <!-- Botones -->
        <div class="">
            <div class="botones-gestion d-flex flex-wrap justify-content-between">
                <button type="button" class="btn btn-primary flex-item">BV</button>
                <button type="button" class="btn btn-primary flex-item">NC</button>
                <button type="button" class="btn btn-primary flex-item">ROD</button>
            </div>
        </div>


        
        <div class="form-group row">
          <label for="tipo" class="col-sm-4 col-form-label">Tipo:</label>
          <div class="col-sm-8">
            <select id="tipo" v-model="formData.tipo" class="form-control">
              <option disabled value="">Seleccione el tipo</option>
              <option value="Tipo A">CONTACTO DIRECTO</option>
              <option value="Tipo B">CONTACTO B</option>
            </select>
          </div>
        </div>
  
        
        <div class="form-group row">
          <label for="gestion" class="col-sm-4 col-form-label">Gestión:</label>
          <div class="col-sm-8">
            <select id="gestion" v-model="formData.gestion" class="form-control">
              <option disabled value="">Seleccione una gestión</option>
              <option value="Gestión A">COMP. DE PAGO ABONO</option>
              <option value="Gestión B">Gestión B</option>
            </select>
          </div>
        </div>
        
        <div class="box-compromisoFecha-pago d-flex flex-wrap">
        
        <div class="form-group col-md-6">
          <label for="compromisoMonto">Compromiso Monto:</label>
          <input
            type="text"
            id="compromisoMonto"
            v-model="formData.compromisoMonto"
            class="form-control"
          />
        </div>

        
        <div class="form-group col-md-6">
          <label for="fechaPagoCuando">Para Cuando:</label>
          <input
            type="date"
            id="fechaPagoCuando"
            v-model="formData.fechaPagoCuando"
            class="form-control"
          />
        </div>
      </div>
  
        
        <div class="form-group row">
          <label for="comentario" class="col-sm-4 col-form-label">Comentario:</label>
          <div class="col-sm-8">
            <textarea
              id="comentario"
              v-model="formData.comentario"
              class="form-control"
            ></textarea>
          </div>
        </div>
  
        <div class="box-botones d-flex flex-wrap justify-content-between">
            <button type="submit" class="btn btn-success flex-item">Enviar</button>
            <button type="button" class="btn btn-primary flex-item">Salir</button>
        </div>

      </form>
    </div>
 </template>
  
<script>
import '../assets/css/formIngresoGestion.css'; // Ajusta la ruta según la estructura de tu proyecto

    export default {
        name: "FormIngresoGestion",
        data() {
        return {
            formData: {
            negocio: "",
            usuario: "",
            fecha: "",
            telefono: 0,
            direccion:"",
            tipo: "",
            gestion: "",
            compromisoMonto: "",
            fechaPagoCuando: "",
            comentario: "",
            BV: "",
            NC: "",
            ROD: "",
            },
        };
        },
        methods: {
        submitForm() {
            console.log("Formulario enviado con los datos:", this.formData);
            alert(`Datos enviados: ${JSON.stringify(this.formData, null, 2)}`);
        },
        },
    };
</script>
  
