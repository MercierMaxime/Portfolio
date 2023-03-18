<script setup>
    import { reactive, ref, onMounted } from 'vue';

    // Import d'un graphique typeLineChart
    import { Line } from 'vue-chartjs'

    // Import des objets du graphique de la bibliothèque ChartJs
    // Voir documentation pour descriptif des éléments
    import { Chart as ChartJS, Title, Tooltip, Legend,  PointElement, LineElement, 
            LineController, CategoryScale, LinearScale, Filler } from 'chart.js'

    // Eléments utilisés par notre graphique registration pour Vue-chart
    ChartJS.register(Title, Tooltip, Legend, PointElement, LineElement, 
        LineController, CategoryScale, LinearScale, Filler )


    // Propriétés du graphique Utilisés dans le template (props)
    // On définit pour chacune son type de données et sa valeur par défaut
    // On peut utiliser une grande variété de types, voire des objets
    const propChart = defineProps({
        chartId:            { type: String,         default: 'line-chart'      }, // Id du graphique
        datasetIdKey:       { type: String,         default: 'label'          }, // id du dataSet
        width:              { type: Number,         default: 100              }, // Hauteur du graphe
        height:             { type: Number,         default: 40             }, // Largeur du graphe
        cssClasses:         { type: String,         default: ''               }, // Classes css utilisées
        styles:             { type: Object,         default: () => {}         }, // Styles utilisés
        plugins:            { type: Object,         default: () => {}         }  // plugins utilisés
    })

    // Données injectées dans le graphique
    let chartData = reactive({
        // Etiquettes l'axe 
        labels: [ 'Indemne', 'Blessé léger', 'Blessé hospitalisé', 'Tué' ],
        // Valeurs des données du graphique
        // 3 datasets, en un premier temps les données sont statiques (jeux de test)
        // Elles seront écrasées par les données réelles provenant de l'API
        datasets: [
            {
                // Etiquette du jeu de données à projeter
                label : 'Strasbourg',
                // Valeurs des données (statiques pour l'exemple)
                data: [38, 302, 27, 5],
                borderColor: 'rgba(255, 0, 0, 0.5)',
                tension: 0.5,      
                fill:true
            },
            {
                // Etiquette du jeu de données à projeter
                label : 'Dijon',
                // Valeurs des données (statiques pour l'exemple)
                data: [2, 11, 11, 0],
                borderColor: 'rgba(0, 0, 255, 0.5)',
                tension: 0.5,
                fill:true
            },
            {
                // Etiquette du jeu de données à projeter
                label : 'Montpellier',
                // Valeurs des données (statiques pour l'exemple)
                data: [10, 64, 26, 1],
                borderColor: 'rgba(253, 108, 158, 0.5)',
                tension: 0.5,
                fill:true
            },
            {
                // Etiquette du jeu de données à projeter
                label : 'Rennes',
                // Valeurs des données (statiques pour l'exemple)
                data: [14, 247, 54, 4],
                borderColor: 'rgba(255, 255, 0, 0.5)',
                tension: 0.5,
                fill:true
            },
            {
                // Etiquette du jeu de données à projeter
                label : 'Besançon',
                // Valeurs des données (statiques pour l'exemple)
                data: [6, 43, 16, 0],
                borderColor: 'rgba(0, 128, 0, 0.4)',
                tension: 0.5,
                fill:true
            }
        ]
    });

    // Options du graphique
    // Les principales utilisées, ils en existe beaucoup d'autres
    // voir documentation
    let chartOptions = reactive({ 
        // Aspect responsive du graphique
        responsive: true,  

        scales:{
            // axe des ordonnées
           y: {
                // Valeur max des y fixées à 100
                suggestedMax: 350,
                // graduation de l'axe y
                ticks: {
                    // Police
                    font:{
                        size:16
                    }
                }                
           },
           // axe des abscisses
           x:{
                // graduation de l'axe x
                ticks: {
                    // Police
                    font:{
                        size:16 
                    }
                }                
           }
        },

         // Les plugins
         plugins:{
            // Titre du graphique      
            title:{
                // Affichage
                display:true,
                // Libellé du graphique
                text : "Nombre d'accidents dans les agglomérations françaises (2014 - 2018)",
                // Police du texte
                font:{
                    size:16
                }
            }
        } 

    });
</script>

<template>
    <!-- 
        chart-options : Options du graphique
        chart-data : données du graphique
        chart-id : Identifiant du graphique
        dataset-id-key : Identifiant des données
        plugins : plugins utilisés
        css-classes : Classes css utilisées
        styles : styles css utilisés
        width : largeur du graphique
        height : hauteur du graphique
    -->
    <Line
        :chart-options="chartOptions" 
        :chart-data="chartData"
        :chart-id="chartId"
        :dataset-id-key="datasetIdKey"
        :plugins="plugins"
        :css-classes="cssClasses"
        :styles="styles"
        :width="width"
        :height="height"
    />
</template>