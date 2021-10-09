# Recuperação de Senha

## **Requisitos Funcionais (RF)**

- O usuário deve poder recuperar sua senha informando seu e-mail;
- O usuário deve receber um e-mail com instruções de recuperação de senha;
- O usuário deve poder resetar sua senha;

## **Requisitos Não Funcionais (RNF)**

- Utilizar Mailtrap para testar envios de e-mail em ambiente de desenvolvimento;
- Utilizar Amazon SES para envios em produção;
- O envio de e-mails deve acontecer em segundo plano (background job);

## **Regra de Negócio (RN)**

- O link enviado por e-mail para resetar senha, deve expirar em 2h;
- O usuário precisa confirma a nova senha ao resetar sua senha;

# Atualização dp perfil

## **Requisitos Funcionais (RF)**

- O usuário deve poder atualizar seu nome, e-mail e senha;

## **Regra de Negócio (RN)**

- O usuário não pode alterar seu e-mail para um e-mail já utilizado;
- Para atualizar sua senha, o usuário deve informar a senha antiga;
- Para atualizar sua senha, o usuário precisa confirmar a nova senha;

# Painel do Prestador

## **Requisitos Funcionais (RF)**

- O usuário deve poder listar seus agendamentos de um dia específico;
- O prestador deve receber uma notificação sempre que hover um novo agendamento;
- O prestador deve poder visualizar as notificações não lidas;

## **Requisitos Não Funcionais (RNF)**

- Os agendamentos do prestador no dia devem ser armazenados em cache;
- As notificações do prestador devem ser armazenadas no MongoDB;
- As notificações do prestador devem ser enviadas em tempo-real utilizando Socket.io;

## **Regra de Negócio (RN)**

- A notificação deve ter um status de lida ou não-lida para que o prestador possa controlar;

# Agendamento de Serviços

## **Requisitos Funcionais (RF)**

- O usuário deve poder lista todos prestadores de serviços cadastrados;
- O usuário deve poder listar os dias de um mês com pelo menos um horário disponível de um prestador;
- O usuário deve poder listar horários disponíveis de um dia específico de um prestador;
- O usuário deve poder realizar um novo agendamento com um prestador;

## **Requisitos Não Funcionais (RNF)**

- A listagem de prestadores deve ser armazenada em cache;

## **Regra de Negócio (RN)**

- Cada agendamento deve durar 1h exatamente;
- Os agendamentos devem estar disponíveis entre 8h às 18h (Primeiro às 8h, último às 17h);
- O usuário não pode agendar em um horário já ocupado;
- O usuário não pode agendar em um horário que já passou;
- O usuário não pode agendar serviços consigo mesmo;
