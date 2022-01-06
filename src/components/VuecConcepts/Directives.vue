<template lang="" >
    <div class="IfDirec">
        <h2 v-if="number===0">If statement number is 0</h2>
        <h2 v-else-if="number===1">else if statement number is 1 </h2>
        <h2 v-else-if="number===2">else if statement number is 2</h2>
        <h2 v-else>else statement</h2>
        <h4>displaying list of contents when number is > 0</h4>
        <div v-if="number>0">
            <h4>Gopi</h4>
            <h4>Reddy</h4>
            <h4>Bajjuri</h4>
        </div>
        <h4>displaying list of contents using v show</h4>
         <div v-show="showElemets">
            <h4>Gopi</h4>
            <h4>Reddy</h4>
            <h4>Bajjuri</h4>
        </div>
    </div>

    <div class="VueFor">
        <h2>FOR DIRECTIVE</h2>   
        <div>
            <h3><u>For directive for array of strings</u></h3>
            <h4 v-for="(name,index) in names" :key="name">{{index}} {{name}}</h4>
        </div>
        <div>
            <h3><u>displaying list of contents based on condition</u></h3>
            <div v-for="name in names" :key="name">
                <h4 v-if="name ==='G'"> {{insex}} {{name}}</h4>
            </div>
        </div>
        <div>
            <h3><u>For directive for array of objects</u></h3>
            <h4 v-for="name in fullNames" :key="name.list">{{name.first}} {{name.last}}</h4>
        </div>
    
        <div>
            <h3><u>For directive for array of arrays</u></h3>
            <div v-for="user in users" :key="user">
                <h3>{{user.name}} </h3>
                <h3 v-for="(place,index,key) in user.Places" :key="place">{{index}} {{key}} {{place}}</h3>
             </div>
        </div>
   </div>
   <div>
       <!-- the diff is whenever the change render in ui the total ui will render by using methods
       by using computed if independent property chnged in ui computed property wont render  -->
        <h3>COMPUTED PROPERTIES</h3>
        <h4>fullname: {{firstName}} {{lastName}}</h4>
        <h4> computed fullname: {{fullname}}</h4>
        <h4> Total - {{items.reduce((total,curr)=>(
            total = total + curr.price),0)}}</h4>
        <h4>computed total : {{totalPrice}}</h4> 

        <h3><u>COMPUTED PROPERTIES for v-for</u></h3>
        <h4> expensive items which are greater than 500 items :</h4>
        <h4 v-for="item in items" :key="item.id">
            <h5 v-if="item.price < 600">item: {{item.title}} price : {{item.price}}</h5>
        </h4>
        <h5 v-for="item in expensiveItems" :key="item.id">by computed
            item: {{item.title}} price : {{item.price}}     
         </h5>
        <div>
          <h4>
            computed fullNmae : {{fullName}}
            <button @click= "changefullName()">ChnageFullName</button>
          </h4>

        </div>
    </div>
</template>




<script>
export default {
  name: "Directives",
  data() {
    return {
      number: Math.floor(Math.random() * 3),
      showElemets: true,
      firstName: "Gopi",
      lastName: "Reddy",
      items: [
        {
          id: 1,
          title: "Bus",
          price: 250,
        },
        {
          id: 2,
          title: "Train",
          price: 500,
        },
        {
          id: 3,
          title: "Flight",
          price: 2500,
        },
      ],

      names: ["Gopi", "Ssr", "N"],
      fullNames: [
        { first: "Bajjuri", last: "Gopi" },
        { first: "Bajjuri", last: "Nikhila" },
      ],
      users: [
        {
          name: "B Govardhan",
          Places: ["23-8-2019", "24-8-2019"],
        },
        {
          name: "B gopi",
          Places: ["BVK Multiplex", "Uppal"],
        },
      ],
    };
  },
  methods: {
    changefullName() {
      this.fullName = 'Govardhan Reddy'
      
    }
  },
  computed: {
    fullname() {
      return `${this.firstName} ${this.lastName}`;
    },
    fullName:{
      get(){
        return `${this.firstName} ${this.lastName}`
      },
      set(value){
        // const name =  value.split('')
        console.log(value);
        this.firstName = value[0]
        this.lastName = value[1]
      }
    },

    totalPrice() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
    expensiveItems() {
      return this.items.filter((item) => item.price < 600);
    },
  },
};
</script>



<style>
.IfDirec {
  background-color: lightblue;
}

.VueFor {
  background-color: lightblue;
}
</style>