<template>
  <div>
    <div class="container-fluid">
      <div class="row mt-5">
        <div class="col-lg-3 border border-primary">
        <p class="bg-info text-uppercase pl-3 text-white">Paga o que deves</p>
         
          <div class="mb-3">
            <label for="nomeUtilizador" class="form-label">Nome</label>
            <input 
              v-model="novaDespesa.nome"
              type="text"
              class="form-control"
              id="nomeUtilizador"
              placeholder="Informe o seu nome"
              required>
          </div> 

          <div class="mb-3">
            <label for="categoria" class="form-label">Categoria</label>
            <input
              v-model="novaDespesa.categoria"
              type="text" 
              class="form-control" 
              id="categoria" 
              placeholder="Informe o nome da categoria" 
              required>
          </div>  

          <div class="mb-3">
            <label for="Descricao" class="form-label">Descrição</label>
            <input
              v-model="novaDespesa.desc"
              type="text" 
              class="form-control" 
              id="Descricao" 
              required>
          </div>  

          <div class="mb-3">
            <label for="valor" class="form-label">Valor</label>  
            <input
            v-model="novaDespesa.valor"
            type="number" 
            class="form-control" 
            id="valor" 
            placeholder="" 
            required>
          </div>  
          
          <div class="mb-3">
            <label for="data" class="form-label">Data</label>  
            <input 
            v-model="novaDespesa.data"
              type="date" 
              class="form-control" 
              id="data" 
              placeholder="" 
              required>
          </div>  

          <div class="mb-3">
            <button 
              type="button" 
              class="btn btn-info">
                Criar despesas
              </button>
          </div>  
        </div>

        <div class="col-lg-9 bg-light">
          <table class="table">
              <thead>
                <tr>
                  <th scope="col">Ord</th>
                  <th scope="col">Nome</th>
                  <th scope="col">Categoria</th>
                  <th scope="col">Descrição</th>
                  <th scope="col">Valor</th>
                  <th scope="col">Data</th>
                  <th scope="col" class="text-center">Opções</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(despesa, index) in listaDespesas" :key="index">
                  <th scope="row">{{listaDespesas.index + 1}}</th>
                  <td>{{despesa.nome}}</td>
                  <td>{{despesa.Categoria}}</td>
                  <td>{{despesa.desc}}</td>
                  <td>{{despesa.valor}}</td>
                  <td>{{despesa.data}}</td>
                  
                  <td>
                       
                  </td>
                </tr>
              </tbody>
            </table>
            
        </div>
        <button
        type="button" 
        class="btn btn-primary btn-sm ml-2"
        @click="AddDespesa()">
        + Detalhes
        </button> 
        <!-- <div>
          <button type="button" class="btn btn-primary">
            Total despesa <span class="badge bg-secondary">4</span>
          </button>
        </div> -->
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  name: 'Despesa',

  computed: {
  },
  data(){
    return{
      listaDespesas: [],
      novaDespesa:{
        nome: '',
        categoria: '',
        desc: '',
        valor: '',
        data: ''
      }
    }
  },
  
  methods: {
    AddDespesa(){
      // eslint-disable-next-line no-debugger
      debugger
      this.listaDespesas.push(this.novaDespesa)
      this.novaDespesa.nome = '',
      this.novaDespesa.categoria='',
      this.novaDespesa.desc='',
      this.novaDespesa.valor='',
      this.novaDespesa.data=''
    }
  },
  created() {

  }
}
</script>

<style scoped>

</style>
