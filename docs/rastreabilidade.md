## Tabela de Rastreabilidade

A tabela abaixo mapeia os requisitos funcionais aos elementos técnicos modelados nos diagramas.

| Requisito (RF) | Entidades (DER) Relacionadas          | Classes Relacionadas                                    |
| :------------- | :------------------------------------ | :------------------------------------------------------ |
| **RF01**       | USUARIO                               | Usuario, Aluno, realizarLogin(), realizarCadastro()     |
| **RF02**       | PROGRESSO, USUARIO (streak, xp_total) | Aluno, Metrica, obterProgressoTrilha()                  |
| **RF03**       | LOG ATIVIDADE                         | Log, Interacao, registrarInteracao()                    |
| **RF04**       | TRILHA, AULA, EXERCICIO, ALTERNATIVA  | Administrador, ConteudoEducacional, cadastrarConteudo() |
| **RF05**       | — (Lógica de Serviço / IA)            | Recomendacao, aplicarModeloIA()                         |
| **RF06**       | AVALIACAO, RESULTADO_AVALIACAO        | AvaliacaoNivel, Questao, ajustarDificuldade()           |
| **RF07**       | TRILHA, AREA_APRENDIZADO              | Trilha, Aluno, escolherTrilha()                         |
| **RF08**       | NOTIFICACAO                           | Notificacao, enviarNotificacao()                        |

---

## Justificativa de Segurança (RNF 03 e RNF 04)

### Ausência da Entidade "Token" no DER
A segurança de autenticação e o controle de acesso são tratados através de **Tokens Stateless (JWT - JSON Web Token)**, o que justifica a não existência de uma tabela física de "Tokens" ou "Sessões" no banco de dados pelos seguintes motivos:

* **Arquitetura Stateless:** O JWT carrega todas as informações de identidade do usuário de forma criptografada. A validação ocorre na camada de aplicação (Middleware), eliminando a necessidade de consultas constantes ao banco de dados para validar sessões ativas.
* **Segurança de Dados:** O campo `senha_hash` na entidade `USUARIO` (conforme visto no DER) garante que as senhas nunca sejam armazenadas em texto plano, cumprindo as boas práticas de criptografia.
* **Níveis de Acesso:** A separação de privilégios entre `Aluno` e `Administrador` (conforme visto no Diagrama de Classes através da herança) permite que o sistema controle o que cada usuário pode visualizar ou editar sem depender de uma tabela de tokens.