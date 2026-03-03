# Requisitos Funcionais (RF)
1. O sistema deve permitir que o usuário realize cadastro e login por e-mail e senha.
2. O sistema deve disponibilizar métricas de desempenho do usuario, como acertos, tempo de estudo e evolução.
3. O sistema deve registrar todas as interções do usuário com conteúdos e atividades.
4. O sistema deve permitir que administradores cadatrem, editem e removam conteúdos educacionais.
5. O sistema deve recomendar conteúdos utilizando um modelo de IA.
6. O sistema deve aplicar avaliações adaptativas, ajustando o nível de dificuldade das questões em tempo real.
7. O sistema deve gerar trilhas de estudo personalizadas com basd no histórco de desempenho do usuário.
8. O sistema deve enviar notificações ao usu´rio sobre conteúdos, prazos e recomendações da IA.

# Requisitos Não Funcionais
1. A interface deve ser responsiva, garantindo usabilidade em dispositivos desktop e móveis.
2. Ao salvar o perfil (Cadastrar), o sistema deve fornecer feedback imediato ao usuário, sem necessidade de recarregar toda a página.
3. A tela inicial deve carregar os indicadores (Streak, XP, Progresso) e a seção “O que estudar hoje” em até 2 segundos, em condições normais de uso.
4. As configurações do perfil devem ser persistidas em banco de dados e recuperadas corretamente ao acessar novamente a página Perfil.
5. O sistema deve utilizar HTTPS para proteção de dados e controle de sessão autenticada.
6. Deve haver controle de acesso, permitindo que apenas o aluno autenticado visualize e edite seus próprios dados e progresso.
7. O sistema deve garantir consistência nos cálculos de XP, Progresso (%) e Streak, impedindo valores inconsistentes ou negativos.
8. O sistema deve registrar logs de ações relevantes, como salvar perfil, iniciar aula e acessar a Mentoria IA.