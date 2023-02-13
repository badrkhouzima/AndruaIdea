<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <input type="range" :min="min" :max="max" v-model="selectedValue"/>
      <!-- <p>{{ selectedValue }}</p> -->
      <h4>{{this.vidaLaboral[selectedValue].desde}}-{{this.vidaLaboral[selectedValue].hasta}}</h4>
      <h1>{{ this.vidaLaboral[selectedValue].cargo }}</h1>
      <p>{{ this.vidaLaboral[selectedValue].descripcion }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  computed: {
    min() {
      //we can chnage this.vidaLaboral[0].id; with 0 in the min input because it's always starts from 0
      return this.vidaLaboral[0].id;
    },
    max() {
      return this.vidaLaboral[this.vidaLaboral.length - 1].id;
    }
  },
  data() {
    return {
      selectedValue: 0,
      vidaLaboral: [
        {
          id: "01",
          diseñador: "before",
          desde: "2001",
          hasta: "2001",
          duracion: "2 meses",
          cargo: "Aprendiz de mécanico de compresores de aire",
          empresa: "DICELMAC AUTOMATISMES S.L.",
          descripcion:
            "Fue mi primer trabajo. Uno de esos trabajos de verano, durante las vacaciones del curso, donde aprovechas el tiempo para ganas tu primer salario. Mi función en la empresa fue limpiar piezas y servir herramientas al mecánico que montaba los compresores",
        },
        {
          id: "02",
          diseñador: "before",
          desde: "2002",
          hasta: "2002",
          duracion: "2 meses",
          cargo: "Operario en rebobinadora de papel de celulosa",
          empresa: "CRISWEN, S.A.",
          descripcion:
            "Mi función en la empresa era cargar la máquina de papel, rebobinar el papel y extraer el producto para su empaquetado",
        },
        {
          id: "03",
          diseñador: "before",
          desde: "2003",
          hasta: "2003",
          duracion: "2 meses",
          cargo: "Operario de carretilla",
          empresa: "ALMACENES DIA%",
          descripcion:
            "Estuve en el equipo de descarga de camiones con carretilla elevadora",
        },
        {
          id: "04",
          diseñador: "before",
          desde: "2004",
          hasta: "2005",
          duracion: "1 año",
          cargo: "Responsable de almacén y logística de equipos de montadores",
          empresa: "MOBLES PANORAMA S.A.",
          descripcion:
            "Al finalizar mis estudios en la Escuela Municipal de Arte y Diseño (EMAD) de La Garriga, estuve trabajando un año para poder sacarme el carnet B y poder seguir estudiando. Ese trabajo, a parte de darme libertad económica, me hizo crecer como trabajador. Por primera vez, por necesidad y casualidad, fui el responsable de sección de una empresa. Recepcionaba el producto de los proveedores, lo almacenaba por clientes minimizando el poco espacio que había y organizaba los grupos de trabajo y sus rutas de clientes.",
        },
        {
          id: "05",
          diseñador: "before",
          desde: "2006",
          hasta: "2008",
          duracion: "2 años",
          cargo: "Responsable de almacén",
          empresa: "SAURMIDECOR S.A.",
          descripcion:
            "Por razones familiares, mis estudios se vieron afectados y tuve que volver al mundo laboral. Por suerte había tenido una buena experiencia en la última empresa y los compañeros me recomendaron en una empresa más grande, también en el sector de la logística y mobiliario. Mi cargo consistía en la organización del equipo de almacén, inventario y distribución de reparto a los transportistas",
        },
        {
          id: "06",
          diseñador: "before",
          desde: "2009",
          hasta: "2010",
          duracion: "2 temporadas de 6 meses",
          cargo: "Cocinero",
          empresa: "CAFÈ EL PILAR",
          descripcion:
            "A raíz de la crisis económica de 2008, estuve en el paro y aproveché para estudiar un curso de Macromedia. Una vez acabado el curso me fui a buscar trabajo de temporada a las islas Baleares. Allí encontré un trabajo de cocinero, algo que a nivel laboral, nunca había hecho. Es cierto que como hobby si había hecho mis cosas en mi cocina, pero en aquel trabajo estuve solo ante el peligro. Diseñar menú, preparación y logística de los productos y cocinar en servicios de mañana y tarde-noche",
        },
        {
          id: "07",
          diseñador: "before",
          desde: "2010",
          hasta: "2015",
          duracion: "5 años",
          cargo: "Oficial de primera en cartonaje para alimentación",
          empresa: "MEDIOAMBIENTE PACK S.A.",
          descripcion:
            "Un familiar me recomendó para entrar en esta empresa de Valencia. Nada más llegar sustituí a la persona que se encargaba de la impresora. Poco a poco fui conociendo toda la maquinaria de la empresa y llegué a llevar equipos de trabajo en las onduladoras de papel. Una de mis tareas era estandarizar los diferentes procesos de producción de cuatro de las siete máquinas que había en aquella empresa",
        },
        {
          id: "08",
          diseñador: "after",
          desde: "2016",
          hasta: "2018",
          duracion: "2 años",
          cargo: "Diseñador gráfico",
          empresa: "VIENTO NORTE SUR",
          descripcion:
            "Fue mi primer trabajo como diseñador gráfico. La organización Viento Norte Sur, que se dedica a la coordinación de viajes solidarios por todo el mundo, me propuso rediseñar su branding y la UX de la web. Estuve trabajando con ellos mientras cursaba el Grado superior en Gráfica Interactiva",
        },
        {
          id: "09",
          diseñador: "after",
          desde: "2018",
          hasta: "2019",
          duracion: "1 año",
          cargo: "Diseñador gráfico",
          empresa: "SIMBÒLIC COMUNICACIÓ",
          descripcion:
            "Después de cursar el primer Ciclo Formativo de Grado Superior en diseño, tuve la suerte de quedarme en la empresa donde hice las prácticas. Allí me encargaría del branding de algunos clientes. Diseño y rediseño de logotipos, maquetación editorial y algún que otro trabajo audiovisual. Estuve trabajando con ellos mientras cursaba mi segundo curso de Grado Superior en Gráfica Publicitaria",
        },
        {
          id: "10",
          diseñador: "after",
          desde: "2019",
          hasta: "2020",
          duracion: "1 año",
          cargo: "Diseñador gráfico",
          empresa: "PHOENIX TEEFACTORY S.L.",
          descripcion:
            "Una vez acabada mi formación como diseñador gráfico, me contrató una empresa de serigrafía y estampación de camisetas en el departamento de diseño gráfico. Allí haría tratamiento de imagenes, preparación de archivos para fotolitos y soporte en laboratorio de insolación",
        },
        {
          id: "11",
          diseñador: "after",
          desde: "2020",
          hasta: "2022",
          duracion: "2 años",
          cargo: "Diseñador gráfico y soporte en taller de serigrafía",
          empresa: "GLOBAL MANAGING S.L.U.",
          descripcion:
            "La oleada pandémica dejó a las empresas tocadas. Por suerte me contrataron en Global Managing para llevar el proyecto de ecommerce. Hasta que no empezó el proyecto, estuve encargandome del taller de entelaje",
        },
        {
          id: "11",
          diseñador: "after",
          desde: "2022",
          hasta: "hoy",
          duracion: "Trabajando",
          cargo: "Diseñador gráfico Frontend",
          empresa: "Autónomo",
          descripcion:
            "La oleada pandémica dejó a las empresas tocadas. Por suerte me contrataron en Global Managing para llevar el proyecto de ecommerce. Hasta que no empezó el proyecto, estuve encargandome del taller de entelaje",
        },
      ],
    };
  },
};
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
