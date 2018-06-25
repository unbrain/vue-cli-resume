<template>
  <div id="Preview">
    <div class="left">
      <h2>DESCRIPTION</h2>
      <hr>
      <p>
        Cristian graduated in February 2014 as senior technician in the field of Higher National Diploma in advertising graphic. (CFGS in Spain)advertising graphics on ESD Orihuela, Alicante (Spain). He finished studies ESDO, Orihuela, Alicante, Spainwith the highest possible mark in your final project. Since September 2013, he lives and works in Murcia for the Krealia Communication company as Access Testshead of graphic design.
      </p>
      <h2>CONTACT ME</h2>
      <hr>
      <section v-for="item in resume.phones">
        <h3>{{item.name}}</h3>
        <p>{{item.number}}</p>
        <hr>
      </section>

    </div>
    <div class="right">
      <h1>{{resume.idcard.name}}</h1>
      <h2 class="work">{{resume.idcard.job}}</h2>

      <h2>EXPERTIENCE</h2>
      <hr>
      <div class="education-container" v-for="item in resume.companys">
        <div class="education-left">
          <h4>{{item.when}}</h4>
        </div>
        <div class="education-right">
          <h4>{{item.job}}</h4>
          <p>{{item.experience}}</p>
        </div>
      </div>
      <h2>EDUCATION</h2>
      <hr>
      <div class="education-container" v-for="item in resume.schools">
        <div class="education-left">
          <h4>{{item.name}}</h4>
          <div>{{item.when}}</div>
        </div>
        <div class="education-right">
          <h4>{{item.professional}}</h4>
          <p>{{item.experience}}</p>
        </div>
      </div>
      <h2>PROJECT</h2>
      <hr>
      <div class="education-container" v-for="item in resume.projects">
        <div class="education-left">
          <h4>{{item.name}}</h4>
        </div>
        <div class="education-right">
          <h4>{{item.skills}}</h4>
          <p>{{item.description}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['resume'],
  methods: {
    filter(items) {
      return items.filter(item => !this.isEmpty(item))
    },
    isEmpty(obj) {
      let empty = true
      for (let key in obj) {
        if (obj[key].trim()) {
          empty = false
          break
        }
      }
      return empty
    }
  }
}
</script>

<style lang="scss">
#Preview {
  display: flex;
  height: inherit;
  min-width: 940px;
  max-width: 1024px;
  margin-left: 16px;
  flex: 1;
  background-color: #363636;
  overflow: auto;
}
.left {
  width: 30%;
  display: flex;
  flex-direction: column;
  padding: 32px;
  color: #f7f7f7;
  p {
    color: #e3e3e3;
    margin-top: 8px;
    text-align: justify;
  }
  hr {
    margin: 16px 0;
    border: 1px solid #666666;
  }
  h2 {
    margin-top: 24px;
  }
}
.right {
  z-index: 1;
  flex: 1;
  padding: 32px;
  color: #3e3e40;
  background-color: #fff;
  h1 {
    font-size: 40px;
    margin: 0;
    padding: 8px 0;
  }
  h2 {
    color: #2e2e2e;
    padding: 8px 0;
  }
  .work {
    padding-bottom: 32px;
  }
  .education-container {
    padding: 8px;
    display: flex;
    h4 {
      padding-bottom: 8px;
    }
    .education-left {
      width: 30%;
      padding-right: 32px;
      display: flex;
      flex-direction: column;
      align-items: flex-end;
    }
    .education-right {
      flex: 1;
      width: 40%;
    }
  }
}
</style>
