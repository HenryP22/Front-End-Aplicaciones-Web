<template>
  <div>
    <h1 class="title">Creacion de tarjeta</h1>
    

    <Loader v-if="isLoading" />
    <form v-else @submit.prevent="save">


      <div class="field">
        <input
          :class="{error: validation.hasError('model.fecha_expiracion')}"
          v-model="model.fecha_expiracion"
          class="input"
          type="date"
          placeholder="Ingrese el fecha expiracion"
        />
        <p class="help is-danger">{{validation.firstError('model.fecha_expiracion')}}</p>
      </div>
      <div class="field">
        <input
          :class="{error: validation.hasError('model.nombre_poseedor')}"
          v-model="model.nombre_poseedor"
          class="input"
          type="text"
          placeholder="Ingrese la nombre poseedor"
        />
        <p class="help is-danger">{{validation.firstError('model.nombre_poseedor')}}</p>
      </div>
      
      <div class="field">
        <input
          :class="{error: validation.hasError('model.numero_tarjeta')}"
          v-model="model.numero_tarjeta"
          class="input"
          type="text"
          placeholder="Ingrese la numero tarjeta"
        />
        <p class="help is-danger">{{validation.firstError('model.numero_tarjeta')}}</p>
      </div>

      
      <div class="field">
        <button type="submit" class="button is-info">Guardar</button>
      </div>
    </form>
    <td class="has-text-centered">
      <button  type="submit" styles="margin-top:20px;background-color:green"><router-link to="/tarjetas">Cancelar</router-link></button>
      </td>
  </div>
</template>

<script src="./TarjetaCreate.js"></script>
