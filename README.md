# Mission Control AI — missão Evortex

Integrantes:
Matheus Sabino da Silva Guedes – RM: 572907
Lucas Bellezzo Figueiredo - RM: 569734

⬡ MISSÃO EVORTEX — Mission Control AI
Sobre o Sistema
A Missão EVORTEX é um sistema completo de monitoramento ambiental de uma cápsula espacial experimental, desenvolvido como projeto acadêmico. O sistema integra hardware real, interface web futurista e inteligência artificial conversacional para simular o controle de uma missão espacial do início ao fim.
Na prática, um Arduino Uno coleta dados de quatro sensores físicos instalados na cápsula — gás, fogo, luminosidade e temperatura — e transmite essas informações em tempo real via porta serial USB para uma interface web construída com HTML, CSS e JavaScript puro. Essa interface exibe os dados em cards interativos, gráficos de linha atualizados continuamente, histórico de eventos exportável e uma cápsula espacial animada que muda de estado conforme os alertas detectados.
Quando qualquer sensor ultrapassa um limite crítico, o sistema reage de forma automática: o Arduino aciona o buzzer físico de emergência (pino D6), a interface abre um popup de alerta com o protocolo de resposta passo a passo para aquela situação específica — incêndio, vazamento de gás, falha de iluminação ou temperatura crítica — e o chatbot de IA é notificado para orientar o operador em tempo real.
O projeto também conta com um Modo Simulação completo, que permite demonstrar todos os cenários de crise sem precisar do Arduino conectado, tornando o sistema funcional para apresentações acadêmicas em qualquer ambiente.

Como a IA está envolvida
A inteligência artificial no sistema EVORTEX se manifesta através da ARIA — Artificial Response & Intelligence Assistant — um chatbot conversacional embutido diretamente na interface web e também disponível como módulo Python independente no notebook.
A ARIA não é uma IA genérica. Ela possui uma base de dados construída especificamente para esta missão, com conhecimento detalhado sobre cada componente do sistema: o que é a Missão EVORTEX, como funciona cada sensor fisicamente, quais são os limites operacionais de cada leitura, a fórmula matemática usada para calcular a temperatura pelo termistor NTC, como o código Arduino toma decisões, como usar cada botão da interface, como conectar o hardware e quais ações tomar em cada tipo de emergência.
Essa base de dados cobre 20 tópicos estruturados e é consultada por um motor de linguagem natural que interpreta perguntas em texto livre — sem precisar de conexão com servidores externos ou APIs pagas. Quando o operador digita "o que é essa missão?", "como funciona o sensor de fogo?" ou "o que devo fazer com temperatura crítica?", a ARIA identifica o contexto e responde com informação técnica precisa e contextualizada.
Além de responder perguntas, a ARIA tem comportamento proativo: sempre que um popup de alerta crítico é acionado, ela envia automaticamente uma mensagem no chat notificando quais sistemas falharam e orientando o operador a consultar os protocolos de resposta. Se a janela do chat estiver fechada, um indicador visual no botão flutuante avisa que há uma mensagem pendente.
No notebook Python, a mesma base de conhecimento da ARIA está disponível como um módulo interativo de terminal, permitindo conversar com ela diretamente no Google Colab — útil para demonstrações acadêmicas, estudos e apresentações.
A escolha por uma IA local e baseada em regras, em vez de um modelo de linguagem externo, foi deliberada: garante que o sistema funcione completamente offline, sem latência de rede, sem custo de API e com respostas sempre precisas e controladas — adequado para um contexto de missão onde confiabilidade é essencial.


prints reais do sistema rodando:




Como executar Com interface web e Arduino real

Grave o arquivo missao_evortex.ino no Arduino Uno via Arduino IDE Abra o arquivo missao_evortex.html no Google Chrome ou Microsoft Edge Selecione o modo Real no topo da interface Clique em ⬡ Conectar Arduino e escolha a porta COM Os dados dos sensores aparecerão nos cartões em tempo real

Sem Arduino — modo de demonstração

Abra missao_evortex.html no Chrome ou Edge Selecione o modo Simulação Use os botões de simulação manual ou clique em ▶ Auto Todos os alertas, popups e o chatbot ARIA funcionam normalmente

Sistema Python no terminal bashpython3 mission_control_ai.py Para usar o chatbot ARIA com IA: bashexport ANTHROPIC_API_KEY="sua-chave-aqui" python3 mission_control_ai.py Google Colab Abra o notebook no Google Colab: https://colab.research.google.com/drive/1scF9jG0XkSZzlaHrsKrzoH7flY186i6a Execute as células em ordem. A interface e o chatbot ARIA estarão disponíveis diretamente no ambiente do Colab.

1 ## Vídeo de Demonstração
https://youtu.be/-J4D0HJUrEg?si=kgBXOJa-it9eB_DT
