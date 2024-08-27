<template>
   <div class="container-fluid">
            <div class="row">
                <div class="col-lg-12">
                    <div class="card-transparent card-block card-stretch card-height mb-3">
                        <div class="d-flex justify-content-between">                             
                            <div class="select-dropdown input-prepend input-append">
                                <div class="btn-group">
                              <b-dropdown  id="dropdownMenuButton1"  offset="65"  right variant="none p-0" data-toggle="dropdown" class="dropdown shadow-none "  no-caret > 
                                <template v-slot:button-content>
                                    <label data-toggle="dropdown" class="m-0">
                                    <div class="dropdown-toggle search-query">My Drive<i class="las la-angle-down ml-3"></i></div><span class="search-replace"></span>
                                    <span class="caret"><!--icon--></span>
                                    </label>
                                 </template>
                          <b-dropdown-item class="pt-2 pb-2"  ><i class="ri-folder-add-line pr-3"></i>{{ ('New Folder') }} </b-dropdown-item>
                          <hr class="m-0">
                          <b-dropdown-item  class="pt-2 pb-2"   ><i class="ri-file-upload-line pr-3"></i>{{ ('Upload Files') }}</b-dropdown-item>
                          <hr class="m-0">
                          <b-dropdown-item  class="pt-2 pb-2" ><i class="ri-folder-upload-line pr-3"></i>{{ ('Upload Folders') }}</b-dropdown-item>
                        </b-dropdown>
                                </div>
                            </div>
                           <DropdownToggle />
                        </div>
                    </div>
                </div>
                <div class="col-lg-8">
                    <div class="card card-block card-stretch card-height iq-welcome" :style="`background: url(${require('@/assets/images/layouts/mydrive/background.png')}) no-repeat scroll right center; background-color: #ffffff; background-size: contain;`">
                        <div class="card-body property2-content">
                            <div class="d-flex flex-wrap align-items-center">
                                <div class="col-lg-6 col-sm-6 p-0">
                                    <h3 class="mb-3">Welcome Penny</h3>
                                    <p class="mb-5">You have 32 new notifications and 23 unread messages to reply</p>
                                    <a href="#">Try Now<i class="las la-arrow-right ml-2"></i></a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4">
                    <div class="card card-block card-stretch card-height">
                        <div class="card-header d-flex justify-content-between">
                            <div class="header-title">
                                <h4 class="card-title">Quick Access</h4>
                            </div>
                        </div>
                        <div class="card-body">
                            <ul class="list-inline p-0 mb-0 row align-items-center">
                                <li class="col-lg-6 col-sm-6 mb-3 mb-sm-0"> 
                                    <div :data-url="`${baseUrl}/doc-viewer/files/demo.pdf`" data-title="Product-planning.pdf" @click="$root.$emit('bv::show::modal', 'viewer-modal', $event.target)" v-b-modal.viewer-modal style="cursor: pointer;" class="p-2 text-center border rounded">
                                        <div>
                                            <img src="@/assets/images/layouts/mydrive/folder-1.png" class="img-fluid mb-1" alt="image1">
                                        </div>
                                        <p class="mb-0">Planning</p>
                                    </div>
                                </li>
                                <li class="col-lg-6 col-sm-6"> 
                                    <div :data-url="`${baseUrl}/doc-viewer/files/demo.docx`" data-title="Wireframe.docx" @click="$root.$emit('bv::show::modal', 'viewer-modal', $event.target)" v-b-modal.viewer-modal style="cursor: pointer;" class="p-2 text-center border rounded">
                                        <div>
                                            <img src="@/assets/images/layouts/mydrive/folder-2.png" class="img-fluid mb-1" alt="image2">
                                        </div>
                                        <p class="mb-0">Wireframe</p>
                                    </div>
             
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>                             
                <div class="col-lg-12">
                    <div class="card card-block card-stretch card-transparent ">
                        <div class="card-header d-flex justify-content-between pb-0">
                            <div class="header-title">
                                <h4 class="card-title">Documents</h4>
                            </div>
                            <div class="card-header-toolbar d-flex align-items-center">
                                <a href="./recent" class=" view-more">View All</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-3 col-md-6 col-sm-6">
                    <div class="card card-block card-stretch card-height">
                        <div class="card-body image-thumb">
                            <a href="#" data-title="Terms.pdf" :data-url="`${baseUrl}/doc-viewer/files/demo.pdf`" @click="$root.$emit('bv::show::modal', 'viewer-modal', $event.target)" v-b-modal.viewer-modal>
                                <div class="mb-4 text-center p-3 rounded iq-thumb">
                                    <div class="iq-image-overlay"></div>
                                    <img src="@/assets/images/layouts/page-1/pdf.png" class="img-fluid" alt="image1">       
                                </div>
                                <h6>Terms.pdf</h6> 
                            </a>             
                        </div>
                    </div>
                </div>
                <div class="col-lg-3 col-md-6 col-sm-6">
                    <div class="card card-block card-stretch card-height">
                        <div class="card-body image-thumb">
                            <a href="#" data-title="New-one.docx" :data-url="`${baseUrl}/doc-viewer/files/demo.docx`" @click="$root.$emit('bv::show::modal', 'viewer-modal', $event.target)" v-b-modal.viewer-modal>
                            <div class="mb-4 text-center p-3 rounded iq-thumb">
                                <div class="iq-image-overlay"></div>
                                <img src="@/assets/images/layouts/page-1/doc.png" class="img-fluid" alt="image1">
                            </div>
                            <h6>New-one.docx</h6>  
                            </a>
                        </div>
                    </div>
                </div>
                <div class="col-lg-3 col-md-6 col-sm-6">
                    <div class="card card-block card-stretch card-height">
                        <div class="card-body image-thumb">
                            <a href="#" data-title="Woo-box.xlsx" :data-url="`${baseUrl}/doc-viewer/files/demo.xlsx`" @click="$root.$emit('bv::show::modal', 'viewer-modal', $event.target)" v-b-modal.viewer-modal>
                                <div class="mb-4 text-center p-3 rounded iq-thumb">
                                    <div class="iq-image-overlay"></div>
                                    <img src="@/assets/images/layouts/page-1/xlsx.png" class="img-fluid" alt="image1">
                                </div>
                                <h6>Woo-box.xlsx</h6>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="col-lg-3 col-md-6 col-sm-6">
                    <div class="card card-block card-stretch card-height">
                        <div class="card-body image-thumb doc-text">
                            <a href="#" data-title="IOS-content.pptx" :data-url="`${baseUrl}/doc-viewer/files/demo.pptx`" @click="$root.$emit('bv::show::modal', 'viewer-modal', $event.target)" v-b-modal.viewer-modal>
                            <div class="mb-4 text-center p-3 rounded iq-thumb">
                                <div class="iq-image-overlay"></div>
                                <img src="@/assets/images/layouts/page-1/ppt.png" class="img-fluid" alt="image1">      
                            </div>
                            <h6>IOS-content.pptx</h6>   
                            </a>       
                        </div>
                    </div>
                </div>
                <div class="col-lg-12">
                    <div class="card card-block card-stretch card-transparent">
                        <div class="card-header d-flex justify-content-between pb-0">
                            <div class="header-title">
                                <h4 class="card-title">Folders</h4>
                            </div>
                            <div class="card-header-toolbar d-flex align-items-center">
                                <b-dropdown  id="dropdownMenuButton1" right variant="none p-0" data-toggle="dropdown" class="dropdown shadow none ">
                                <template v-slot:button-content>
                                   <span class="dropdown-toggle dropdown-bg btn bg-white" id="dropdownMenuButton1"
                                        data-toggle="dropdown">
                                        Name<i class="ri-arrow-down-s-line ml-1"></i>
                                    </span>
                                 </template>
                                <b-dropdown-item>{{ ('Last modified') }}</b-dropdown-item>
                                <b-dropdown-item>{{ ('Last modifiedby me') }}</b-dropdown-item>
                                <b-dropdown-item>{{ ('Last opened by me') }}</b-dropdown-item>
                              </b-dropdown> 
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 col-sm-6 col-lg-3"  v-for="(folder,index) in Folders" :key="index" >
                    <div class="card card-block card-stretch card-height" >
                        <div class="card-body"  >                            
                                <div class="d-flex justify-content-between">
                                    <router-link :to="folder.link" class="folder">
                                        <div :class="folder.color">
                                            <i class="ri-file-copy-line"></i>
                                        </div>
                                    </router-link>
                                    <div class="card-header-toolbar">
                                        <b-dropdown  id="dropdownMenuButton1" right variant="none p-0" data-toggle="dropdown" class="dropdown shadow none ">
                                                <template v-slot:button-content>
                                                    <span class="dropdown-toggle" id="dropdownMenuButton2" data-toggle="dropdown">
                                                        <i class="ri-more-2-fill"></i>
                                                    </span>
                                                </template>
                                                <b-dropdown-item><i class="ri-eye-fill mr-2"></i>{{ ('view') }}</b-dropdown-item>
                                                <b-dropdown-item><i class="ri-delete-bin-6-fill mr-2"></i>{{ ('delete') }}</b-dropdown-item>
                                                <b-dropdown-item><i class="ri-pencil-fill mr-2"></i>{{ ('edit') }}</b-dropdown-item>
                                                <b-dropdown-item><i class="ri-printer-fill mr-2"></i>{{ ('print') }}</b-dropdown-item>
                                                <b-dropdown-item><i class="ri-file-download-fill mr-2"></i>{{ ('download') }}</b-dropdown-item>
                                        </b-dropdown>
                                    </div>
                                </div>
                                <router-link :to="folder.link" class="folder">
                                    <h5 class="mb-2">{{folder.name}}</h5>
                                    <p class="mb-2"><i :class="folder.clock "></i>{{folder.date}}</p>
                                    <p class="mb-0"><i :class="folder.filecolor"></i> {{folder.file}}</p>
                                </router-link>
                           
                        </div>
                    </div>
                </div>
                <div class="col-lg-8 col-xl-8"> 
                    <div class="card card-block card-stretch card-height files-table">                   
                        <div class="card-header d-flex justify-content-between">
                            <div class="header-title">
                                <h4 class="card-title">Files</h4>
                            </div>
                            <div class="card-header-toolbar d-flex align-items-center">
                                <router-link to="./files" class=" view-more">View All</router-link>
                            </div>
                        </div>
                        <div class="card-body pt-0">
                            <div class="table-responsive">
                                <table class="table mb-0 table-borderless tbl-server-info">
                                <thead>
                                    <tr>
                                        <th scope="col">Name</th>
                                        <th scope="col">Members</th>
                                        <th scope="col">Last Edit</th>
                                        <th scope="col">Size</th>
                                        <th scope="col"></th>
                                    </tr>
                                </thead>
                                <tbody>
                                     <tr v-for="(file ,index) in  Files" :key="index"  :class="file.extraclass">
                                        <td>
                                            <div class="d-flex align-items-center">
                                                <div :class="file.color">
                                                    <i :class="file.icon"></i>
                                                </div>
                                                <a href="#"  :data-title="file.name" :data-url="file.url" @click="$root.$emit('bv::show::modal', 'viewer-modal', $event.target)" v-b-modal.viewer-modal >
                                                <span style="color:#535F6B;">{{file.name}}</span>
                                                </a>
                                            </div>
                                        </td>
                                        <td>{{file.owner}}</td>
                                        <td>{{file.lastEdit}}</td>
                                        <td>{{file.size}}</td>
                                        <td>
                                                <b-dropdown  id="dropdownMenuButton1" right variant="none p-0" data-toggle="dropdown" class="dropdown shadow none ">
                                                    <template v-slot:button-content>
                                                        <span class="dropdown-toggle" id="dropdownMenuButton2" data-toggle="dropdown">
                                                        <i class="ri-more-fill"></i>
                                                        </span>
                                                        </template>
                                                    <b-dropdown-item><i class="ri-eye-fill mr-2"></i>{{ ('view') }}</b-dropdown-item>
                                                    <b-dropdown-item><i class="ri-delete-bin-6-fill mr-2"></i>{{ ('delete') }}</b-dropdown-item>
                                                    <b-dropdown-item><i class="ri-pencil-fill mr-2"></i>{{ ('edit') }}</b-dropdown-item>
                                                    <b-dropdown-item><i class="ri-printer-fill mr-2"></i>{{ ('print') }}</b-dropdown-item>
                                                    <b-dropdown-item><i class="ri-file-download-fill mr-2"></i>{{ ('download') }}</b-dropdown-item>
                                            </b-dropdown>
                                        </td>
                                    </tr>
                                </tbody>
                                </table>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4">
                    <div class="card card-block card-stretch card-height ">
                        <div class="card-header d-flex justify-content-between">
                            <div class="header-title">
                                <h4 class="card-title">Statistic</h4>
                            </div>
                        </div>
                        <div class="card-body">
                          
                             <AmChart element="layout-1-chart" type="dashboard1chart"  />
                            <div class="row mt-4">
                                <div class="col-lg-6 col-md-6 col-6">
                                    <div class="media align-items-center">
                                        <div class="icon iq-icon-box bg-primary rounded icon-statistic">
                                            <i class="las la-long-arrow-alt-down"></i>
                                        </div>
                                        <div class="media-body ml-3">
                                            <p class="mb-0">Downloads</p>
                                            <h5>12,594</h5>
                                        </div>
                                    </div>
                                </div>
                                <div class="col-lg-6 col-md-6 col-6">
                                    <div class="media align-items-center">
                                        <div class="icon iq-icon-box bg-light rounded icon-statistic">
                                            <i class="las la-long-arrow-alt-up"></i>
                                        </div>
                                        <div class="media-body ml-3">
                                            <p class="mb-0">Uploads</p>
                                            <h5>1,458</h5>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4">
                    <div class="card card-block card-stretch card-height  plan-bg">
                        <div class="card-body">
                            <h4 class="mb-3 text-white">Unlock Your plan</h4>    
                            <p>Expanded Storage, Access To<br> More Features On </p>   
                            <div class="row align-items-center justify-content-between">
                               <div class="col-6 go-white ">
                                <a href="#" class="btn d-inline-block mt-5">Go Premium</a>
                               </div>
                                <div class="col-6">
                                    <img src="@/assets/images/layouts/mydrive/lock-bg.png" class="img-fluid" alt="image1">
                                </div>
                            </div>                     
                        </div>
                    </div>
                </div>
                <div class="col-lg-8">
                    <div class="card card-block card-stretch card-height">
                        <div class="card-header d-flex justify-content-between pb-0">
                            <div class="header-title">
                                <h4 class="card-title">Storage</h4>
                            </div>
                            <div class="card-header-toolbar d-flex align-items-center">
                         <b-dropdown  id="dropdownMenuButton1" right variant="none p-0" data-toggle="dropdown" class="dropdown shadow-none">
                          <template v-slot:button-content>
                               <span class="dropdown-toggle btn  dropdown-bg border border-primary text-primary rounded" id="dropdownMenuButton11"
                                        data-toggle="dropdown">
                                        Monthly<i class="ri-arrow-down-s-line ml-1"></i>
                                 </span>
                          </template>
                          <b-dropdown-item>{{ ('Monthly') }}</b-dropdown-item>
                          <b-dropdown-item>{{ ('Weekly') }}</b-dropdown-item>
                           <b-dropdown-item>{{ ('Yearly') }}</b-dropdown-item>
                        </b-dropdown>
                            </div>
                        </div>
                        <div class="card-body pt-0">
                              <ApexChart element="layout-1-chart2" :chartOption="chart1" />
                         
                        </div>
                    </div>
                </div>
            </div>
        </div>
</template>
<script>
import AmChart from '../../../components/charts/AmChart'
 import ApexChart from '../../../components/charts/ApexChart'
export default {
    name:'Dashbord1',
    components:{
         ApexChart,
         AmChart
    },
    data(){
        return{
             Folders:[
                {
                    
                    link:"./alexworkshop",
                    color:"icon-small bg-danger rounded mb-4 ",
                    name:"Alexa Workshop",
                    date:"10 Dec, 2020",
                    file:"08 Files",
                     clock:"lar la-clock text-danger mr-2 font-size-20",
                    filecolor:"las la-file-alt text-danger mr-2 font-size-20"
                },
                {
                    
                    link:"./android",
                    color:"icon-small bg-primary rounded mb-4 ",
                    name:"Android",
                    date:"09 Dec, 2020",
                    file:"08 Files",
                     clock:"lar la-clock text-primary mr-2 font-size-20",
                    filecolor:"las la-file-alt text-primary mr-2 font-size-20"
                },
                 {
                    
                    link:"./brightspot",
                    color:"icon-small bg-info rounded mb-4 ",
                    name:"Brightspot",
                    date:" 07 Dec, 2020",
                    file:"08 Files",
                     clock:"lar la-clock text-info mr-2 font-size-20",
                    filecolor:"las la-file-alt text-info mr-2 font-size-20"
                },
                 {
                    
                    link:"./ionic-chat-app",
                    color:"icon-small bg-success rounded mb-4 ",
                    name:"Ionic Chat App",
                    date:" 06 Dec, 2020",
                    file:"08 Files",
                     clock:"lar la-clock text-success mr-2 font-size-20",
                    filecolor:"las la-file-alt text-success mr-2 font-size-20"
                }
            ],
             Files:[
               {
                   icon:"ri-file-excel-line",
                   color:"icon-small bg-danger rounded mr-3",
                   name:"Weekly-Report.pdf",
                   url:this.baseUrl+"/doc-viewer/files/demo.pdf",
                   owner:"Me",
                   lastEdit:"jan 21, 2020 me",
                   size:"02 MB"
               },
               {
                   extraclass:"active",
                   icon:"ri-file-download-line",
                   color:"icon-small bg-primary rounded mr-3",
                   name:"Vuejs.pdf",
                   url:this.baseUrl+"/doc-viewer/files/demo.pdf",
                   owner:"Poul Molive",
                   lastEdit:"jan 25, 2020 Poul Molive",
                   size:"64 MB"
               },
                {
                   icon:"ri-file-excel-line",
                   color:"icon-small bg-info rounded mr-3",
                   name:"Milestone.docx",
                   url:this.baseUrl+"/doc-viewer/files/demo.docx",
                   owner:"Me",
                   lastEdit:"Mar 30, 2020 Gail Forcewind",
                   size:"30 MB"
               },
                {
                   icon:"ri-file-excel-line",
                   color:"icon-small bg-success rounded mr-3",
                   name:"Training center.xlsx",
                   url:this.baseUrl+"/doc-viewer/files/demo.xlsx",
                   owner:"Me",
                   lastEdit:"Mar 30, 2020 Gail Forcewind",
                   size:"10 MB"
               },
                {
                   icon:"ri-file-excel-line",
                   color:"icon-small bg-warning rounded mr-3",
                   name:"Flavour.pptx",
                   url:this.baseUrl+"/doc-viewer/files/demo.pptx",
                   owner:"Me",
                   lastEdit:"Mar 30, 2020 Gail Forcewind",
                   size:"10 MB"
               }
            ],
            chart1:{
                series: [{
                    name: "Desktops",
                    data: [10, 35, 25, 60, 59, 25, 55, 20, 35]
                }],
                colors: ["#8f93f6"],
                    chart: {
                    toolbar: {
                        show: false
                    },
                    height: 225,
                    type: 'line',
                    zoom: {
                    enabled: false
                    }
                },
                dataLabels: {
                    enabled: false
                },
                stroke: {
                    curve: 'straight'
                },
                title: {
                    text: '',
                    align: 'left'
                },
                grid: {
                    row: {
                    colors: ['#f3f3f3', 'transparent'], 
                    opacity: 0.5
                    },
                },
                xaxis: {
                    categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep'],
                    labels: {
                    minHeight: 20,
                    maxHeight: 20
                    }
                },
                yaxis: {
                    show: true,
                    labels: {
                        minWidth: 15,
                        maxWidth: 15
                    }
                    }
            },
           
        }
    },
    methods: {
    }
}
</script>
