<template>
  <div>
    <h1 class="title">Módulo de docentes</h1>
    <h2 class="subtitle">Desde aquí puede gestionar sus docentes.</h2>

    <Loader v-if="isLoading" />
    <template v-else>
      <div class="field has-text-right">
        <router-link to="/docentes/create">Agregar nuevo docente</router-link>
      </div>
      <table class="table is-striped is-fullwidth">
        <thead>
          <th style="width:50px;" class="has-text-centered">Docente</th>
          <th style="width:200px;" class="has-text-left">Nombres</th>
          <th style="width:200px;" class="has-text-left">Apellidos</th>
          <th style="width:200px;" class="has-text-left">Correo</th>
          <th style="width:200px;" class="has-text-left">Disponibilidad</th>
          <th style="width:200px;" class="has-text-left">Membresía</th>
          <th style="width:150px;"></th>  
        </thead>
        <tbody>
          <tr v-for="item in collection.items" :key="item.id">
            <td class="has-text-centered"> {{item.docenteId}}</td>
            <td class="has-text-left"> {{item.nombres}}</td>
            <td class="has-text-left"> {{item.apellidos}}</td>
            <td class="has-text-left"> {{item.correo}}</td>
            <td class="has-text-left"> {{item.disponibilidad}}</td>
            <td class="has-text-left"> {{item.membresia}}</td>
            <td class="has-text-centered">
              <router-link :to="`/docentes/${item.docenteId}/detail`">Ver detalle</router-link>
            </td>
          </tr>
        </tbody>
      </table>
      <Pager :paging="p => getAll(p)" :page="collection.page" :pages="collection.pages" />
    </template>
  </div>
</template>

<script src="./DocenteIndex.js"></script>