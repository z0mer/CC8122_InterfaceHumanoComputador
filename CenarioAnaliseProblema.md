# Narrativa: Sincronização de Dados Biométricos sob Pressão no Box
Durante uma sessão de testes no Autódromo de Interlagos, o piloto Humberto retorna ao box visivelmente frustrado, reclamando que não consegue manter a constância na curva 3. 
O ambiente é hostil: o ruído dos motores é alto, impedindo qualquer comunicação sonora eficiente, e o calor no pit lane aumenta a ansiedade da equipe.

Anna, a engenheira de dados, precisa extrair rapidamente os dados dos óculos de rastreamento ocular (Pupil Core) de Humberto para entender o que está acontecendo. 
No entanto, o processo atual é fragmentado. Enquanto o hardware da Racelogic oferece vídeo e telemetria, e o Smart Eye fornece métricas de atenção, essas ferramentas não "conversam" entre si.

Anna tenta baixar os logs do veículo e os arquivos do eye tracker em seu notebook, que está apoiado precariamente em uma pilha de pneus. 
Ela sente uma ansiedade paralisante enquanto tenta alinhar manualmente os timestamps do vídeo com os picos de aceleração e freio da telemetria, sabendo que a equipe tem apenas 5 minutos 
para ajustar o setup antes do próximo treino.

Neste cenário problemático, a falta de uma ferramenta única que faça a ingestão e o merge automático dos dados gera um risco alto de erro humano. 
Humberto está impaciente e quer ver no replay onde olhou errado, mas Anna ainda está lutando com arquivos CSV desconexos. Sem a sincronização automática, os dados de carga cognitiva (dilatação da pupila) 
perdem a validade ecológica, pois não podem ser correlacionados com precisão ao exato momento em que Humberto enfrentou um obstáculo na pista.
