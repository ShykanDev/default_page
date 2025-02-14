<template>
    <div class="">
        <MainLayout>
            <template #main>
                <section class="flex flex-wrap justify-around">

                    <IngredientsCard v-for="ingredient in ingredients" :key="ingredient.mainTitle"
                        :mainTitle="ingredient.mainTitle" :smallIntro="ingredient.smallIntro"
                        :description="ingredient.description" :imgSrc="ingredient.imgSrc"
                        :infoArr="ingredient.infoArr" />
                </section>
            </template>
        </MainLayout>
    </div>
</template>

<script lang="ts" setup>
import IngredientsCard from '@/components/IngredientsCard.vue';
import MainLayout from '@/layouts/MainLayout.vue';
const ingredients = [
{
  "mainTitle": "Guggul (Commiphora mukul)",
  "smallIntro": "Un ingrediente tradicional usado en la medicina ayurvédica para el manejo del colesterol y la salud cardiovascular.",
  "description": "El Guggul, conocido científicamente como Commiphora mukul, es una resina extraída de la planta Guggul, que crece en las regiones secas de la India, Pakistán y Bangladesh. Este ingrediente ha sido utilizado durante siglos en la medicina ayurvédica para tratar diversas dolencias, especialmente aquellas relacionadas con el sistema cardiovascular. Es famoso por sus propiedades antiinflamatorias y antioxidantes, ayudando a reducir el colesterol malo (LDL) y aumentar el colesterol bueno (HDL). También se utiliza para mejorar la circulación sanguínea y fortalecer las arterias, lo que contribuye a una mejor salud cardiovascular.",
  "imgSrc": "https://storage.googleapis.com/a1aa/image/7ajZ2e2XRDQHcK10GRbeMO3nB4ouR6abROxcmpfZbCirVjrnA.jpg",
  "infoArr": [
    { "id": 1, "property": "Dosis", "description": "60 mg de resina pura de Guggul por día" },
    { "id": 2, "property": "Propiedades", "description": "Anti-inflamatorio, antioxidante, promueve la salud cardiovascular, regula el colesterol" },
    { "id": 3, "property": "Beneficios", "description": "Ayuda a reducir los niveles de colesterol LDL (malo) y triglicéridos, aumenta el colesterol HDL (bueno), mejora la circulación sanguínea y apoya el sistema cardiovascular." },
    { "id": 4, "property": "Usos comunes", "description": "Se utiliza para tratar el colesterol alto, la artritis, la obesidad, y como un remedio natural para mejorar la circulación y la salud del corazón." },
    { "id": 5, "property": "Mecanismo de acción", "description": "El Guggul actúa inhibiendo la producción de grasas en el hígado, reduciendo así los niveles de colesterol. Además, sus propiedades antiinflamatorias ayudan a reducir el riesgo de enfermedades cardíacas." }
  ]
},
{
  "mainTitle": "Extracto de Salai Guggul (Boswellia serrata)",
  "smallIntro": "Conocido por sus propiedades antiinflamatorias y beneficios para las articulaciones.",
  "description": "El extracto de Salai Guggul proviene de la resina de la planta Boswellia serrata, que se encuentra principalmente en las regiones áridas de la India, Medio Oriente y África. Este ingrediente ha sido utilizado en la medicina tradicional para tratar diversas afecciones inflamatorias, especialmente en el tratamiento de artritis, dolor articular y enfermedades inflamatorias intestinales. La resina de Boswellia serrata contiene compuestos activos como los ácidos boswélicos, que ayudan a reducir la inflamación en las articulaciones y promueven la reparación del cartílago. Es ampliamente reconocido por su capacidad para aliviar el dolor articular y mejorar la movilidad en condiciones como la artritis.",
  "imgSrc": "https://storage.googleapis.com/a1aa/image/LaRz6oNN1VbOLpOzgYvPJE4zoCvfkhAVyDGaevT2kG5Wrx1TA.jpg",
  "infoArr": [
    { "id": 1, "property": "Dosis", "description": "10 mg de extracto de Boswellia serrata por día" },
    { "id": 2, "property": "Propiedades", "description": "Anti-inflamatorio, alivia el dolor articular, promueve la salud del cartílago" },
    { "id": 3, "property": "Beneficios", "description": "Ayuda en el tratamiento de la artritis, mejora la movilidad articular, reduce la inflamación y el dolor en las articulaciones." },
    { "id": 4, "property": "Usos comunes", "description": "Es utilizado en el tratamiento de la artritis reumatoide, osteoartritis, dolores musculares y articulares, y en enfermedades inflamatorias del tracto digestivo." },
    { "id": 5, "property": "Mecanismo de acción", "description": "Los ácidos boswélicos presentes en la resina de Boswellia serrata inhiben las enzimas que causan la inflamación en el cuerpo, especialmente en las articulaciones, lo que ayuda a reducir el dolor y mejorar la movilidad." }
  ]
}
,
{
  "mainTitle": "Extracto de Nirgundi (Vitex negundo)",
  "smallIntro": "Un remedio tradicional utilizado para aliviar dolores musculares y de las articulaciones.",
  "description": "El extracto de Nirgundi proviene de la planta Vitex negundo, conocida por sus potentes propiedades analgésicas y antiinflamatorias. En la medicina ayurvédica, se utiliza principalmente para aliviar dolores musculares y articulares, especialmente en casos de artritis y dolores crónicos. Además, el extracto de Nirgundi es conocido por sus efectos relajantes sobre el sistema nervioso, ayudando a reducir los niveles de estrés y promoviendo un bienestar general. Sus hojas y semillas se usan para tratar diversas afecciones inflamatorias y para mejorar la flexibilidad y el rango de movimiento.",
  "imgSrc": "https://storage.googleapis.com/a1aa/image/NHufk6rXCAyWNy4nggG1hwYP13Vsf1NSsZfelEDiEGSQvGXPB.jpg",
  "infoArr": [
    { "id": 1, "property": "Dosis", "description": "120 mg de extracto de Nirgundi por día" },
    { "id": 2, "property": "Propiedades", "description": "Analgesico, anti-inflamatorio, relajante muscular" },
    { "id": 3, "property": "Beneficios", "description": "Alivia dolores musculares y articulares, reduce el estrés, mejora la movilidad y flexibilidad articular." },
    { "id": 4, "property": "Usos comunes", "description": "Tratamiento de la artritis, dolor muscular, dolores de espalda, y como un remedio natural para el estrés y la ansiedad." },
    { "id": 5, "property": "Mecanismo de acción", "description": "El extracto de Nirgundi actúa inhibiendo las prostaglandinas, compuestos responsables de la inflamación y el dolor, mientras que también ayuda a reducir la tensión muscular." }
  ]
},

{
  "mainTitle": "Extracto de Ashwagandha (Withania somnifera)",
  "smallIntro": "Una hierba adaptógena utilizada para mejorar la vitalidad y reducir el estrés.",
  "description": "La Ashwagandha, conocida científicamente como Withania somnifera, es una hierba adaptógena de gran renombre en la medicina ayurvédica. Esta planta se utiliza principalmente para mejorar la resistencia física, reducir el estrés y la ansiedad, y mejorar la función cognitiva. Los adaptógenos como la Ashwagandha ayudan al cuerpo a adaptarse mejor al estrés, tanto físico como emocional. Esta hierba también es conocida por sus propiedades energizantes y por mejorar la calidad del sueño, siendo un remedio popular para la fatiga crónica y el agotamiento mental.",
  "imgSrc": "https://storage.googleapis.com/a1aa/image/jbUJRi88aN5dNJxWBEcFmKUFmMSe9Yx25pDiNVKRf2dRsx1TA.jpg",
  "infoArr": [
    { "id": 1, "property": "Dosis", "description": "25 mg de extracto de Ashwagandha por día" },
    { "id": 2, "property": "Propiedades", "description": "Adaptógena, energizante, reduce el estrés, mejora la función cognitiva" },
    { "id": 3, "property": "Beneficios", "description": "Reduce el estrés y la ansiedad, mejora la función cerebral, aumenta la resistencia física y combate la fatiga." },
    { "id": 4, "property": "Usos comunes", "description": "Se utiliza para el manejo del estrés y la ansiedad, mejora la memoria y concentración, aumenta la energía y vitalidad." },
    { "id": 5, "property": "Mecanismo de acción", "description": "La Ashwagandha actúa modulando los niveles de cortisol, la hormona del estrés, y favorece la recuperación física al mejorar la vitalidad y la energía general del cuerpo." }
  ]
}
,
{
    mainTitle: "Extracto de Erandamool (Ricinus communis)",
    smallIntro: "Conocido por sus propiedades laxantes, desintoxicantes y antiinflamatorias.",
    description: "El Erandamool, también conocido como Ricinus communis o aceite de ricino, es utilizado tradicionalmente en Ayurveda por sus potentes propiedades laxantes y purificadoras. Ayuda a mejorar la digestión, promover la eliminación de toxinas y es eficaz en el tratamiento de trastornos digestivos. Además, se usa en tratamientos para aliviar dolores articulares, musculares y de espalda, gracias a sus propiedades antiinflamatorias.",
    imgSrc: "https://storage.googleapis.com/a1aa/image/HMeqQfeYd1aBqontHKD65lJEzWBjLw2xlBeIjCgeAzKfIbc9E.jpg",
    infoArr: [
        { id: 1, property: "Dosis", description: "33.33 mg" },
        { id: 2, property: "Propiedades", description: "Laxante, desintoxicante, antiinflamatorio, alivia dolores articulares" },
        { id: 3, property: "Beneficios", description: "Ayuda a mejorar la digestión, promueve la eliminación de toxinas, alivia el dolor y reduce la inflamación" },
        { id: 4, property: "Usos terapéuticos", description: "Utilizado en terapias de desintoxicación, tratamiento de estreñimiento, y para aliviar dolores musculares y articulares. También es un auxiliar en la reducción de inflamación y puede mejorar la circulación sanguínea." },
        { id: 5, property: "Origen", description: "El aceite de ricino se obtiene de las semillas de Ricinus communis, una planta originaria de África y Asia. En Ayurveda, se utiliza como parte de terapias de desintoxicación y como remedio para varios trastornos digestivos." }
    ]
},
{
    mainTitle: "Extracto de Rasna (Pluchea lanceolata)",
    smallIntro: "Usada tradicionalmente en Ayurveda para tratar afecciones musculares y de dolor articular.",
    description: "La Rasna, o Pluchea lanceolata, es una planta que se utiliza en Ayurveda principalmente para el tratamiento de afecciones musculares y articulares, gracias a sus potentes propiedades antiinflamatorias y analgésicas. Es muy eficaz para aliviar dolores musculares y articulares crónicos, como en el caso de la artritis y el dolor lumbar. Además, se considera un remedio natural para combatir la fiebre y reducir la inflamación generalizada.",
    imgSrc: "https://storage.googleapis.com/a1aa/image/YbClVfC352XmJStpp85p1KbFYQpslA65q9hQSUmAtnla246JA.jpg",
    infoArr: [
        { id: 1, property: "Dosis", description: "50 mg" },
        { id: 2, property: "Propiedades", description: "Anti-inflamatorio, analgésico, mejora la movilidad articular" },
        { id: 3, property: "Beneficios", description: "Alivia dolores musculares y articulares, mejora la movilidad y reduce la inflamación articular" },
        { id: 4, property: "Usos terapéuticos", description: "Se utiliza en el tratamiento de artritis, dolores musculares, fiebre y trastornos inflamatorios. Además, es un excelente remedio para mejorar la circulación en las articulaciones y reducir el dolor asociado a la inflamación crónica." },
        { id: 5, property: "Origen", description: "Originaria del subcontinente indio, la Rasna es una planta herbácea que se utiliza desde hace siglos en la medicina tradicional india (Ayurveda) para tratar diversos trastornos inflamatorios y musculares." }
    ]
},
{
    mainTitle: "Extracto de Shilajit (Betún)",
    smallIntro: "Un potente antioxidante y revitalizante natural conocido por sus efectos revitalizantes y anti-envejecimiento.",
    description: "El Shilajit, conocido también como betún de las rocas, es una resina mineral que se encuentra en las montañas del Himalaya. Es famoso por sus efectos antioxidantes, revitalizantes y energizantes. Se considera una de las sustancias más poderosas en Ayurveda para revitalizar el cuerpo y la mente. Mejora la resistencia física, potencia la energía vital y puede ayudar en la recuperación muscular después del ejercicio intenso, además de reducir la fatiga y el agotamiento crónico.",
    imgSrc: "https://storage.googleapis.com/a1aa/image/h9JSowxG20rEE1vpD8ONZ8LrpXbEWA11UbLJ6CnqYB1e246JA.jpg",
    infoArr: [
        { id: 1, property: "Dosis", description: "20 mg" },
        { id: 2, property: "Propiedades", description: "Antioxidante, revitalizante, energizante, anti-envejecimiento" },
        { id: 3, property: "Beneficios", description: "Aumenta la energía, mejora la recuperación muscular, reduce la fatiga, y promueve el bienestar general" },
        { id: 4, property: "Usos terapéuticos", description: "Es ampliamente utilizado para combatir el cansancio crónico, mejorar la salud mental, reducir el estrés, mejorar la memoria y aumentar el rendimiento físico. Además, es conocido por su capacidad para regular los niveles de azúcar en sangre y apoyar la función inmunológica." },
        { id: 5, property: "Origen", description: "El Shilajit se obtiene principalmente de las montañas del Himalaya y el Tíbet, donde se forma durante siglos por la descomposición de plantas y material orgánico bajo presiones geológicas. En Ayurveda, se utiliza como un rejuvenecedor general y un tónico para la vitalidad." }
    ]
}
,
{
    mainTitle: "Extracto de Haldi (Curcuma longa)",
    smallIntro: "Una raíz conocida por sus potentes propiedades antiinflamatorias, antioxidantes y digestivas.",
    description: "La cúrcuma, o Haldi, es una de las hierbas más potentes en Ayurveda. Su compuesto activo, la curcumina, es reconocido por sus propiedades antiinflamatorias, antioxidantes y digestivas. Se utiliza para reducir la inflamación, mejorar la salud general, aliviar dolores articulares y musculares, y también tiene un potente efecto antioxidante que protege las células del daño causado por los radicales libres. Además, se ha demostrado que mejora la digestión y apoya la salud del sistema inmunológico.",
    imgSrc: "https://storage.googleapis.com/a1aa/image/1VekLpoeUEl8KkGWRex62IWVtcTvaPkcNknSv6xjw16MojrnA.jpg",
    infoArr: [
        { id: 1, property: "Dosis", description: "20 mg" },
        { id: 2, property: "Propiedades", description: "Anti-inflamatorio, antioxidante, digestivo" },
        { id: 3, property: "Beneficios", description: "Reduce la inflamación, mejora la salud celular, alivia dolores articulares y musculares, protege contra el daño celular y apoya la salud digestiva" },
        { id: 4, property: "Usos terapéuticos", description: "En Ayurveda, el Haldi es utilizado como remedio para afecciones inflamatorias, como la artritis, para mejorar la circulación y como un auxiliar digestivo. También se usa como antioxidante para prevenir el envejecimiento prematuro y apoyar la salud cardiovascular." },
        { id: 5, property: "Origen", description: "Originaria del sureste asiático, la cúrcuma es una planta ampliamente cultivada en la India, donde se ha utilizado en la medicina tradicional durante siglos para una variedad de condiciones." }
    ]
},
{
    mainTitle: "Extracto de Adrak (Zingiber officinale)",
    smallIntro: "Una raíz con propiedades digestivas, antiinflamatorias y analgésicas.",
    description: "El Adrak, o jengibre, es una planta reconocida por sus potentes efectos digestivos y antiinflamatorios. Contiene compuestos como el gingerol, que le confiere propiedades antiinflamatorias, analgésicas y antioxidantes. Se utiliza en Ayurveda para mejorar la digestión, aliviar el malestar estomacal, reducir la inflamación y aliviar dolores musculares y articulares. Además, el Adrak puede ayudar a mejorar la circulación sanguínea y fortalecer el sistema inmunológico.",
    imgSrc: "https://storage.googleapis.com/a1aa/image/GpGkTgOkRzatJNieafmNDi841gBXDDWMyHVsuNJNNn0c0x1TA.jpg",
    infoArr: [
        { id: 1, property: "Dosis", description: "20 mg" },
        { id: 2, property: "Propiedades", description: "Digestivo, anti-inflamatorio, analgésico" },
        { id: 3, property: "Beneficios", description: "Mejora la digestión, alivia el malestar estomacal, reduce el dolor muscular y articular, mejora la circulación y fortalece el sistema inmunológico" },
        { id: 4, property: "Usos terapéuticos", description: "En Ayurveda, el Adrak se usa principalmente para tratar trastornos digestivos como la indigestión, el malestar estomacal y la náusea. También se utiliza para aliviar dolores articulares y musculares, así como para reducir la inflamación." },
        { id: 5, property: "Origen", description: "El jengibre es originario del sudeste asiático, especialmente de India y China, y se cultiva ampliamente en todo el mundo por sus numerosos beneficios para la salud." }
    ]
}
,
{
    mainTitle: "Extracto de Pippali (Piper longum)",
    smallIntro: "Utilizado en Ayurveda para mejorar la digestión y la absorción de nutrientes.",
    description: "El Pippali, o Piper longum, es una variedad de pimienta negra que se utiliza en la medicina ayurvédica para mejorar la digestión y aumentar la absorción de nutrientes. Actúa como un potente estimulante digestivo, ayudando a aliviar los problemas digestivos y estimulando la producción de enzimas. Además, se utiliza para tratar afecciones respiratorias como el asma y la tos crónica, y también tiene propiedades antioxidantes que contribuyen a la salud general. Es especialmente eficaz cuando se combina con otras hierbas o especias.",
    imgSrc: "https://storage.googleapis.com/a1aa/image/zZPHvD28AsIkF5fd1XnHkI3fpGytex2ym3YCHQu5kITdpjrnA.jpg",
    infoArr: [
        { id: 1, property: "Dosis", description: "6 mg" },
        { id: 2, property: "Propiedades", description: "Digestivo, mejora la absorción de nutrientes, antioxidante" },
        { id: 3, property: "Beneficios", description: "Ayuda en la digestión, aumenta la absorción de nutrientes y mejora la función respiratoria" },
        { id: 4, property: "Usos terapéuticos", description: "En Ayurveda, el Pippali es utilizado para tratar problemas digestivos, como indigestión y gases, y también se usa para aliviar problemas respiratorios, como asma y tos crónica. Además, se cree que ayuda a aumentar la potencia de otras hierbas y suplementos al mejorar la biodisponibilidad." },
        { id: 5, property: "Origen", description: "Originario de la India y el sudeste asiático, el Pippali ha sido utilizado durante siglos en la medicina tradicional por sus múltiples propiedades curativas." }
    ]
},
{
    mainTitle: "Probiótico (Lactobacillus sporogenes)",
    smallIntro: "Un probiótico utilizado para mejorar la flora intestinal y la salud digestiva.",
    description: "Lactobacillus sporogenes es una cepa de bacterias probióticas que ayuda a mantener un equilibrio saludable de microorganismos en el intestino. Su principal función es mejorar la flora intestinal, lo que facilita una digestión más eficiente y favorece la absorción de nutrientes. Además, este probiótico contribuye a la salud del sistema inmune y tiene propiedades que ayudan a prevenir o tratar trastornos digestivos, como el estreñimiento, la diarrea o el síndrome del intestino irritable.",
    imgSrc: "https://storage.googleapis.com/a1aa/image/Aou2lPYliD4lP5laRQfXSe6HjQdtdIlAVa5Y3Gld6sufpjrnA.jpg",
    infoArr: [
        { id: 1, property: "Dosis", description: "22 millones de UFC" },
        { id: 2, property: "Propiedades", description: "Probiótico, mejora la salud digestiva, fortalece el sistema inmune" },
        { id: 3, property: "Beneficios", description: "Promueve una flora intestinal saludable, mejora la digestión y ayuda a prevenir trastornos digestivos como el estreñimiento y la diarrea" },
        { id: 4, property: "Usos terapéuticos", description: "El Lactobacillus sporogenes se utiliza para mejorar el equilibrio bacteriano en el intestino, lo que favorece la digestión, la absorción de nutrientes y la salud general del sistema digestivo. También es útil para tratar y prevenir trastornos como el síndrome del intestino irritable y otros desequilibrios bacterianos." },
        { id: 5, property: "Origen", description: "El Lactobacillus sporogenes es una cepa probiótica natural que se encuentra en una variedad de alimentos fermentados y suplementos dietéticos. Se ha utilizado en diversas culturas para promover la salud intestinal y general." }
    ]
}

];


</script>

<style scoped></style>