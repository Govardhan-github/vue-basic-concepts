<template lang="">
  <div>
    <div>
    <pre> 
        {{JSON.stringify(formvalues,null,2)}}
    </pre>
    
    </div>
    <form @submit.prevent="submitForm" class="form">
    <div class="namediv">
        <label  class="label" for="name">Name</label><br>
        <input class="name" type="text" id="name" v-model.trim.lazy="formvalues.name"  /> 
    </div><br>

    
    <div class="profilediv">
        <label class="label1" for="profile">Profile Summary</label><br>
        <textarea class="name1" type="text" id="name" v-model="formvalues.profileSummary"  /> 
    </div>


    <div class="countrydiv">
        <label class="countrylabel" for="country" >Country</label><br>
        <select  id="country" v-model="formvalues.country" >
            <option>Select a country</option>
            <option value="india">India</option>
            <option value="usa">USA</option>
            <option value="uae">UAE</option>
        </select>
    </div>


    <div class="locationdiv">
        <label for="job-location" >Job Location</label><br>
        <select id="job-location"  v-model="formvalues.jobLocation" >
            <option>Select a country</option>
            <option value="india">India</option>
            <option value="usa">USA</option>
            <option value="uae">UAE</option>
        </select>
    </div>
    <div>
        <label for="age">Age</label><br>
        <input @keyup.enter="submitForm" type="number" id="age"   v-model.number="formvalues.age" />

    </div>
    <div class="workremotediv">
        <label for="remoteWork" >Work</label><br>
        <input type="checkbox" id="remotework" true-value="yes" true-valu="no" v-model="formvalues.remoteWork"/>
        <label for="remotework" >Open to remote work</label>
    </div>
    <div class="skilldiv">
        <label>Skill Set</label><br>
        <input type="checkbox" id="html" value="html"  v-model="formvalues.skillSet" />
        <label for="html">HTML</label>
        <input type="checkbox" id="css" value="css"  v-model="formvalues.skillSet" />
        <label for="css">CSS</label>
        <input type="checkbox" id="js" value="js"  v-model="formvalues.skillSet" />
        <label for="js">Java Script</label>
    </div>

    <div class="expdiv">
        <label>Years Of Expeirence</label><br>
        <input type="radio" id="twoyr" value="0-2"  v-model="formvalues.expeirence" />
        <label for="0-2">0-2</label>
        <input type="radio" id="fiveyr" value="3-5"  v-model="formvalues.expeirence" />
        <label for="3-5">3-5</label>
        <input type="radio" id="tenyr" value="6-10"  v-model="formvalues.expeirence" />
        <label for="6-10">6-10</label>
    </div>
    
    <div class="btn">
        <button class="submitbtn" >Submit</button>
    </div>
    </form>
  </div>
</template>
<script>
export default {
  name: "Forms",
  data() {
    return {
      formvalues: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        expeirence: "",
        age: null,
      },
    };
  },
  methods: {
    submitForm() {
      console.log("values", this.formvalues);
    },
  },
};
</script>
<style >
.form {
  margin-left: 50px;
  background: lightblue;
  height: 540px;
  width: 450px;
  border-radius: 5px;
  border: 2px solid red;
}
.namediv {
  position: relative;
  top: 10px;
}

.label {
  margin-top: 10px;
}
.name {
  width: 70%;
  height: 25px;
}
.label1 {
  margin-top: 20px;
}
.name1 {
  width: 70%;
  max-height: 50px;
}
#remotework {
  margin-left: 10px;
  margin-top: 10px;
}
div {
  margin-top: 10px;
  text-align: start;
  margin-left: 10px;
}
.countrylabel {
  width: 70%;
}
#country {
  width: 70%;
  height: 25px;
}
#job-location {
  width: 70%;
  height: 25px;
}

#html {
  margin-top: 10px;
  margin-left: 10px;
}
#css {
  margin-left: 25px;
}
#js {
  margin-left: 25px;
}

#twoyr {
  margin-top: 10px;
  margin-left: 10px;
}
#fiveyr {
  margin-left: 35px;
}
#tenyr {
  margin-left: 35px;
}

.btn {
  text-align: center;
}
#age {
  width: 70%;
  height: 25px;
}
.submitbtn {
  height: 40px;
  width: 80px;
  text-align: center;
  border-radius: 7px;
  background: blue;
  color: white;
  font-weight: bolder;
  font-size: 15px;
  border: none;
}
</style>