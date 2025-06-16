⚡ Simulador de Bitola de Fios - Instalações Elétricas

📌 Contextualização
Em instalações elétricas, o uso da bitola correta dos condutores é essencial para evitar aquecimento, quedas de tensão ou até incêndios. A bitola depende da corrente elétrica que irá circular e da distância até a carga. Esse app visa facilitar esse cálculo automático para uso didático e técnico.

🎯 Objetivo
Criar um aplicativo que:

🔢 Recebe como entrada:
Corrente elétrica (em Ampères);

Distância da instalação (em metros);

✅ Exibe como saída:
Bitola do fio para 110V (em mm²);

Bitola do fio para 220V (em mm²).

🧮 Fórmulas Utilizadas
Essas fórmulas são baseadas em critérios de queda de tensão aceitável:

dart
Copiar
Editar
double bitola110 = (2 * corrente * distancia) / 294.64;
double bitola220 = (2 * corrente * distancia) / 510.4;
🛠️ Tecnologias Utilizadas
Tecnologia	Finalidade
Dart	Lógica dos cálculos
Flutter	Interface gráfica responsiva
Firebase	(Opcional) Salvar simulações, usuários ou relatórios
Firestore	Banco de dados em nuvem
Firebase Hosting	(Opcional) Publicar versão web do app

💻 Exemplo de Código Dart do Cálculo
dart
Copiar
Editar
Map<String, double> calcularBitolas(double corrente, double distancia) {
  double bitola110 = (2 * corrente * distancia) / 294.64;
  double bitola220 = (2 * corrente * distancia) / 510.4;

  return {
    '110V': bitola110,
    '220V': bitola220,
  };
}
📱 Como executar esse projeto no Flutter + Firebase
✅ Crie o projeto Flutter:

bash
Copiar
Editar
flutter create simulador_bitola
cd simulador_bitola
🔥 Integre com Firebase (como descrito nas respostas anteriores)

✏️ Crie os campos na interface:

TextField para corrente;

TextField para distância;

Botão de "Calcular";

Área para exibir os resultados.

🧾 (Opcional) Salvar simulações no Firestore:

dart
Copiar
Editar
FirebaseFirestore.instance.collection('bitolas').add({
  'corrente': corrente,
  'distancia': distancia,
  'bitola_110v': bitola110,
  'bitola_220v': bitola220,
  'data': Timestamp.now(),
});


![image](https://github.com/user-attachments/assets/9310a824-0ffb-4ffd-868c-b91ea3d98910)

