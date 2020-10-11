<template>
  <div>
  {{ msg }}
  <input type="text" v-model="message"><br>
  Output: <span>{{ message }}</span>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    message: String
  },
  watch: {
        message: function(val, oldVal) {
            const pool = 'y,o,u,m,a,k,e,m,e,h,a,p,p,y,j,d,&,o,c,h,2,j,#,f,d,6,9,f,q,b,a,k,5,3,g,6,4,l,o,o,i,7,z,x,@,l,8,c,s,g,i,n,i,w,w,l,1,r,v,v,n,o,s,a,b,e,t,t,e,r'.split(',');

const target = val.split('');

for (let i = 0; i < target.length; i++) {
  const char = target[i];
  const found = pool.indexOf(char);

  if (char !== ' ' && found === -1) {
    this.message = 'could not complete phrase';
    return;
  }

  delete pool[found];
}

this.message = 'phrase can be made!';
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
