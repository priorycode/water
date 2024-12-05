<script setup>
import { ref } from "vue";

// Lista de preguntas
const questions = [
  // Preguntas existentes
  {
    question: "¿Cuál es la fórmula química del agua?",
    options: ["H2O", "CO2", "O2", "H2SO4"],
    correct: "H2O",
  },
  {
    question: "¿Qué porcentaje de la superficie terrestre está cubierta por agua?",
    options: ["70%", "50%", "90%", "30%"],
    correct: "70%",
  },
  {
    question: "¿Qué tipo de agua es apta para el consumo humano?",
    options: ["Agua dulce", "Agua salada", "Agua destilada", "Agua contaminada"],
    correct: "Agua dulce",
  },
  {
    question: "¿Qué proceso convierte el agua en vapor?",
    options: ["Evaporación", "Condensación", "Precipitación", "Filtración"],
    correct: "Evaporación",
  },
  {
    question: "¿Cuál es el mayor océano del mundo?",
    options: ["Pacífico", "Atlántico", "Índico", "Ártico"],
    correct: "Pacífico",
  },
  {
    question: "¿Qué estado de la materia tiene el agua a 0°C bajo presión normal?",
    options: ["Sólido", "Líquido", "Gas", "Plasma"],
    correct: "Sólido",
  },
  {
    question: "¿Qué propiedad del agua permite que los insectos caminen sobre su superficie?",
    options: ["Tensión superficial", "Viscosidad", "Capilaridad", "Densidad"],
    correct: "Tensión superficial",
  },
  {
    question: "¿Cómo se llama el ciclo por el cual el agua circula por el planeta?",
    options: ["Ciclo hidrológico", "Ciclo del carbono", "Ciclo del oxígeno", "Ciclo del nitrógeno"],
    correct: "Ciclo hidrológico",
  },
  {
    question: "¿Qué porcentaje del agua en la Tierra es salada?",
    options: ["97%", "50%", "75%", "10%"],
    correct: "97%",
  },
  {
    question: "¿Cuál es la molécula que forma el agua?",
    options: ["Dos átomos de hidrógeno y uno de oxígeno", "Un átomo de hidrógeno y dos de oxígeno", "Tres átomos de oxígeno", "Dos átomos de oxígeno y uno de hidrógeno"],
    correct: "Dos átomos de hidrógeno y uno de oxígeno",
  },
  {
    question: "¿Qué proceso convierte el agua salada en agua potable?",
    options: ["Desalinización", "Filtración", "Precipitación", "Condensación"],
    correct: "Desalinización",
  },
  {
    question: "¿Qué tipo de energía utiliza mayormente el ciclo del agua para funcionar?",
    options: ["Energía solar", "Energía eólica", "Energía nuclear", "Energía geotérmica"],
    correct: "Energía solar",
  },
  {
    question: "¿En qué capa de la atmósfera ocurre la mayor parte de la evaporación del agua?",
    options: ["Troposfera", "Estratosfera", "Mesosfera", "Exosfera"],
    correct: "Troposfera",
  },
  {
    question: "¿Cuál es la principal fuente de agua dulce en el planeta?",
    options: ["Glaciares", "Océanos", "Ríos", "Lagos"],
    correct: "Glaciares",
  },
  {
    question: "¿Qué organismo juega un papel clave en la purificación del agua en los ecosistemas?",
    options: ["Microorganismos", "Peces", "Plantas terrestres", "Aves"],
    correct: "Microorganismos",
  }
];

// Variables reactivas
const selectedQuestions = ref([]);
const answers = ref({});
const isSubmitDisabled = ref(true);
const isPopupVisible = ref(false);
const score = ref(null);

// Función para inicializar preguntas
const initializeQuiz = () => {
  selectedQuestions.value = questions
      .sort(() => Math.random() - 0.5) // Chocolatear preguntas
      .slice(0, 5); // Seleccionar 5 preguntas
  answers.value = {}; // Reiniciar respuestas
  isSubmitDisabled.value = true; // Deshabilitar botón de enviar
  score.value = null; // Reiniciar puntaje
  isPopupVisible.value = false; // Ocultar popup
};

// Calcular puntaje
const calculateScore = () => {
  let total = 0;
  selectedQuestions.value.forEach((q, index) => {
    if (answers.value[index] === q.correct) {
      total += 2; // Cada respuesta correcta vale 2 puntos
    }
  });
  score.value = total;
  isPopupVisible.value = true; // Mostrar popup con puntaje
};

// Verificar si todas las preguntas están respondidas
const checkCompletion = () => {
  isSubmitDisabled.value =
      Object.keys(answers.value).length !== selectedQuestions.value.length;
};

// Establecer estilo del card cuando se responde una pregunta
const isQuestionAnswered = (index) => {
  return answers.value[index] ? 'answered' : '';
};

// Inicializar preguntas al cargar el componente
initializeQuiz();
</script>

<template>
  <div class="container-general">
    <section class="quiz-container">
      <h2>Evaluación</h2>

      <div class="container">
        <div class="row">
          <div
              class="col-12"
              v-for="(q, index) in selectedQuestions"
              :key="index"
          >
            <div :class="['question-card', isQuestionAnswered(index)]">
              <h3 class="question-title">
                {{ index + 1 }}. {{ q.question }}
              </h3>

              <div class="answers">
                <div v-for="(option, optIndex) in q.options" :key="optIndex">
                  <label>
                    <input
                        type="radio"
                        :value="option"
                        v-model="answers[index]"
                        @change="checkCompletion"
                    />
                    {{ option }}
                  </label>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Botón para enviar -->
      <button
          :disabled="isSubmitDisabled"
          class="submit-btn"
          @click="calculateScore"
      >
        Ver Nota
      </button>

      <!-- Popup para mostrar puntaje -->
      <div v-if="isPopupVisible" class="popup">
        <div class="popup-content">
          <h3>Tienes un Puntaje de:</h3>
          <p class="poppins-bold">
            {{ score }}
          </p>
          <v-btn @click="initializeQuiz" rounded="xl" size="x-large" block
          >Intentar de Nuevo</v-btn
          >
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.container-general {
  background: #e9f9ff;
}
h2 {
  margin-bottom: 30px;
  font-size: 30px;
}
h3 {
  margin-bottom: 20px;
}
.popup-content p {
  margin-bottom: 30px;
  font-size: 60px;
}
.quiz-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 70px 0;
}
@media (max-width: 768px) {
  .quiz-container {
    padding: 30px 16px;
  }
}

.question-card {
  margin-bottom: 20px;
  padding: 16px;
  border: 1px solid #ccc;
  border-radius: 4px;
  background: white;
}

.question-card.answered {
  background-color: rgba(212, 245, 212, 0.53);
}

.question-title {
  font-weight: bold;
}

.answers {
  margin-top: 10px;
}

.answers label {
  display: block;
  margin-bottom: 10px;
}

.submit-btn {
  margin-top: 20px;
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.submit-btn:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}

.popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup-content {
  background-color: #fff;
  padding: 20px;
  border-radius: 4px;
  text-align: center;
}
</style>
