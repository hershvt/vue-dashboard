<template>
<div class="container-fluid">
    <b-table class="mt-5 table" 
    outlined 
    bordered  
    striped hover 
    :items="data" 
    :fields="label"
    @row-clicked="onRowClick()"
    v-model="value"
    >
    <template #cell(actions)="row">
        <b-button variant="primary" size="md" @click="info(row.item, row.index, $event.target)" >
          Info
        </b-button>
    </template>
    
    </b-table>
        
    <b-modal :id="infoModal.id" :title="infoModal.title" ok-only >
      <pre> <h5>
Working on : {{infoModal.project}}

Project Status : {{infoModal.status}}

Employees on-project : {{infoModal.employee}} 
          </h5></pre>
    </b-modal>
    
</div>
</template>

<script>
export default {
    name : 'list',
    data(){
    return{
        value : '',
        context:null,
       infoModal: {
          id: 'info-modal',
          title: '',
          employee : '',
          project :'',
          status : ''
         
        },
        label:[{ key: 'Task', label: 'Task' }, 
        { key: 'Project', label: 'Project' },
         
         { key: 'actions', label: 'Actions' }
         ],
       
        data:[
            {id: 1, Task : 'Frontend updation', Project: 'Project 1', Status : 'Complete', Employee : 'Sanket, Hersh'},
            {id: 1, Task : 'Backend', Project: 'Project 4', Status : 'Pending', Employee : 'Ajay'},
            {id: 1, Task : 'Add banner', Project: 'Project 5', Status : 'Complete', Employee : 'Ashutosh'},
            {id: 1, Task : 'API', Project: 'Project 7', Status : 'Complete', Employee : 'Sanket'}
        ],
       
        }
    },
    methods:{
        onRowClick(record){
            
            console.log("hello there",record)
        },
         info(item, index, button) {
        this.infoModal.title = `Employee Details: ${index + 1}`
        this.infoModal.content = JSON.stringify(item, null, 2)
        this.infoModal.employee = item.Employee
        this.infoModal.project = item.Project
        this.infoModal.status = item.Status
        this.$root.$emit('bv::show::modal', this.infoModal.id, button)
      },
     
    }
}
</script>

<style scoped>

.table{
      font-family: Avenir, Helvetica, Arial, sans-serif;
      font-size: 21px;
      box-shadow: 0 .19rem 1rem rgba(0,0,0,.19)!important;
     
}
</style>