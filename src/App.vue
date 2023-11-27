<template>
  <div class="fondo">
    <div class="content">
      <div v-for="item in items" :key="item.id" class="item" :class="{ 'expanded': item.expanded }">
        <div class="item-details">
          <h1 class="titulo">{{ item.title }}</h1>
          <p class="subtitulo">{{ item.expanded ? item.descriptionLong : item.descriptionShort }}</p>
          <button class="ver-mas-button" @click="toggleItem(item)">Ver más</button>
          <button class="cerrar-button" v-if="item.expanded" @click="closeItem(item)">x</button>
        </div>
      </div>
    </div>
    <div :class="{ 'header-section': true, 'show': showHeader }">
      <div class="header-content">
        <h1 class="titulo">Medio Ambiente y Sostenibilidad</h1>
        <p class="subtitulo">Descubre formas de cuidar nuestro planeta</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showHeader: false,
      items: [
        {
          id: 1,
          title: 'Ahorro de energía',
          descriptionShort: 'El ahorro de energía es esencial para reducir la huella de carbono. Apaga las luces cuando no las necesites y utiliza dispositivos de bajo consumo energético.',
          descriptionLong: 'El ahorro de energía es clave para reducir la huella de carbono y promover la sostenibilidad ambiental. Aquí hay algunas prácticas que puedes adoptar para contribuir al ahorro de energía:\n\n1.Apaga las luces: Cuando no necesitas iluminación, apaga las luces para reducir el consumo eléctrico.\n\n2. Utiliza dispositivos de bajo consumo: Opta por electrodomésticos y dispositivos electrónicos con certificación de eficiencia energética.\n\n3.Aprovecha la luz natural: Abre cortinas y persianas durante el día para aprovechar la luz natural en lugar de depender de la iluminación artificial.\n\n4. Ajusta la temperatura: Regula la temperatura de tu hogar y utiliza termostatos programables para optimizar el uso de calefacción y aire acondicionado.\n\n5. Desconecta dispositivos en modo de espera: Muchos dispositivos consumen energía incluso cuando están en modo de espera. Desconéctalos cuando no los estés utilizando.\n\nRecuerda que pequeñas acciones cotidianas pueden marcar la diferencia en la conservación de recursos y la protección del medio ambiente. ¡Contribuye al ahorro de energía y ayuda a construir un futuro más sostenible!',
          expanded: false,
        },
        {
          id: 2,
          title: 'Uso del plástico',
          descriptionShort: 'Reduce el uso de plástico. Opta por productos reutilizables y recicla siempre que sea posible.',
          descriptionLong: 'Reducir el uso de plástico es esencial para preservar el medio ambiente. Aquí hay algunos consejos para minimizar tu impacto:\n\n1. Bolsas reutilizables: Usa bolsas reutilizables en lugar de bolsas de plástico desechables al hacer compras.\n\n2. Botellas de agua reutilizables: Opta por botellas de agua reutilizables en lugar de botellas de plástico de un solo uso.\n\n3. Envases reutilizables: Almacena alimentos en envases reutilizables en lugar de envoltorios plásticos.\n\n4. Compra a granel: Reduce el embalaje optando por productos a granel y utilizando tus propios contenedores.\n\n5. Recicla adecuadamente: Asegúrate de reciclar correctamente los productos de plástico y apoya iniciativas de reciclaje local.',
          expanded: false,
        },
        {
          id: 3,
          title: 'Agricultura sostenible',
          descriptionShort: 'Cultiva tus propias verduras. Esto no solo es sostenible, sino también saludable y gratificante.',
          descriptionLong: 'La agricultura sostenible es una práctica que beneficia tanto al medio ambiente como a nuestra salud. Aquí hay algunos consejos para cultivar tus propias verduras de manera sostenible:\n\n1. Huerto en casa: Cultiva tus verduras en un pequeño huerto en casa, incluso si tienes poco espacio.\n\n2. Compostaje: Utiliza el compostaje para convertir los residuos orgánicos en fertilizante natural para tus plantas.\n\n3. Riego eficiente: Opta por sistemas de riego eficientes, como el riego por goteo, para conservar agua.\n\n4. Semillas locales: Utiliza semillas locales y adapta tus cultivos a las condiciones climáticas de tu región.\n\n5. Evita pesticidas químicos: Opta por métodos de control de plagas naturales y evita el uso de pesticidas químicos.',
          expanded: false,
        },
        {
          id: 4,
          title: 'Transporte sostenible',
          descriptionShort: 'Usa transporte público o comparte viajes para reducir las emisiones de carbono.',
          descriptionLong: 'Adoptar hábitos de transporte sostenible es crucial para reducir las emisiones de carbono y mitigar el cambio climático. Aquí hay algunos consejos para un transporte más sostenible:\n\n1. Transporte público: Utiliza el transporte público, como autobuses y trenes, para reducir las emisiones individuales.\n\n2. Carpooling: Comparte viajes con amigos, familiares o compañeros de trabajo para disminuir la cantidad de vehículos en la carretera.\n\n3. Bicicleta y caminar: Opta por la bicicleta o caminar cuando sea posible, especialmente para distancias cortas.\n\n4. Vehículos eficientes: Si necesitas un vehículo, elige uno con eficiencia de combustible o considera opciones eléctricas o híbridas.\n\n5. Planificación de rutas: Planifica tus rutas para optimizar el uso de combustible y evitar embotellamientos.',
          expanded: false,
        }
      ],
    };
  },
  methods: {
    toggleItem(item) {
      // Cambia el estado 'expanded' del ítem y actualiza la descripción
      item.expanded = !item.expanded;
    },
    closeItem(item) {
      // Cierra el ítem al hacer clic en el botón 'x'
      item.expanded = false;
    },
  },
  mounted() {
    setTimeout(() => {
      this.showHeader = true;
    }, 100);
  },
};
</script>

<style scoped>
/* Estilos generales */
body {
  background-image: url('@/components/imagenes/Baner1.jpg');
  background-color: rgb(241, 0, 0);
}

.item.expanded {
  height: 300px; /* Ajusta la altura que prefieras */
  background-image: url('@/components/imagenes/Energia.jpg');
}

.button-container.show {
  top: 0;
}

.header-button:hover {
  transform: scale(1.1);
  background-color: #45a049;
}

.header-section {
  background-image: url('@/components/imagenes/Baner1.jpg');
  background-size: cover;
  background-position: center;
  color: #fff;
  text-align: left;
  margin-left: -8px;
  position: fixed;
  width: 115%;
  height: 180px;
  top: -250px;
  transition: top 0.3s ease-in-out;
  background-color: #1d2c1e;
}

.header-section.show {
  top: 0;
}

.header-content {
  max-width: 800px;
  margin: 0 auto;
}

.titulo {
  font-size: 2.5em;
  margin-bottom: 10px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
}

.subtitulo {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
}

.content {
  margin-top: 180px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.item {
  width: 80%;
  max-width: 1600px;
  height: 150px;
  margin: 20px;
  display: flex;
  align-items: center;
  border-radius: 25px;
  background-color: rgb(1, 161, 41);
  padding: 20px;
  color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s, box-shadow 0.3s;
  background-image: url('@/components/imagenes/fondo.jpg');
}

.item:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
.item-details {
  flex-grow: 2;
}
.fondo{
  background-color: #1d2c1e;
  margin-left: -20px;
  margin-right: -20px;
}
</style>
