<template>
  <div>
    <form>
      <label>Email:</label>
      <input type="email" v-model="email" required />

      <label>Password:</label>
      <input type="password" v-model="password" required />

      <label>Role:</label>
      <select v-model="role">
        <option value="developer">Web Developer</option>
        <option value="designer">Web Designer</option>
      </select>

      <div class="terms">
        <input type="checkbox" v-model="terms" required id="" />
        <label for=""> Accept terms </label>
      </div>
      <div>
        <input type="checkbox" name="" value="mohamed" id="" v-model="names" />
        <label for="">mohamed</label>
      </div>
      <div>
        <input type="checkbox" name="" value="ysn" id="" v-model="names" />
        <label for="">ysn</label>
      </div>
      <div>
        <input type="checkbox" name="" value="maria" id="" v-model="names" />
        <label for="">maria</label>
      </div>
      
      <label>Skills :</label>
      <input type="text" v-model="tempSkill" @keyup ="addSkill" />
      <div v-for="skill in skills" :key="skill" class="pill">
         <p  @click="deletSkill(skill)"> {{skill}}</p>

      </div>
    </form>
    <p>Email: {{ email }}</p>
    <p>password: {{ password }}</p>
    <p>role: {{ role }}</p>
    <p>terms : {{ terms }}</p>
    <p>nams : {{ names }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      eamil: "",
      password: "",
      role: "",
      terms: false,
      names: [],
      tempSkill: "",
      comma:',',
      skills: [],
    };
  },

  methods: {
    addSkill(e) {
    //   console.log(this.tempSkill);
    if ( e.key === ',' && this.tempSkill)
    {
        if (!this.skills.includes(this.tempSkill))
        {
            this.skills.push(this.tempSkill.replace(/,/g,'') )
        }
        
        
        this.tempSkill =''
        
    }
    },
    deletSkill(skill){
        // console.log(skill)
        this.skills.pop(skill)
       
        // for(let i=0;i<this.skills.length;i++)
        // {
        //     // console.log(this.skills[i])
        //     this.skills.pop(this.skills[i])

        // }
        // this.skills.remove()
    }
  },
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input,
select {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
input[type="checkbox"] {
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}
.pill{
    display: inline-block;
    margin: 20px 10px 0 0 ;
    padding: 6px 12px ;
    background-color:#eee;
    border-radius: 5px;
    font-size: 12px;
    letter-spacing:1px;
    font-weight: bold;
    color:#777;
    cursor : pointer;
}
</style>
