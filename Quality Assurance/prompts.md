# Prompts de Testes QA

## 1 Gerar casos de teste para login
# Casos de Teste: Tela de Login

## 🟢 1. Cenários de Sucesso (Caminho Feliz)
- **Login com credenciais válidas:** Inserir e-mail e senha corretos e clicar em "Entrar". O usuário deve ser redirecionado para a Dashboard/Home.
- **Manter conectado (Remember Me):** Marcar a opção "Lembrar de mim" antes de logar. Fechar o navegador, abrir novamente e garantir que a sessão continua ativa.

## 🔴 2. Cenários de Exceção (Validações e Erros)
- **E-mail não cadastrado:** Inserir um e-mail válido no formato, mas que não existe no banco de dados, com uma senha qualquer. O sistema deve exibir a mensagem: *"E-mail ou senha inválidos"*.
- **Senha incorreta:** Inserir um e-mail cadastrado e uma senha errada. O sistema deve exibir a mensagem: *"E-mail ou senha inválidos"* (evitar dizer qual dos dois está errado por motivos de segurança).
- **Campos vazios:** Clicar no botão "Entrar" sem preencher e-mail e senha. O sistema deve exibir alertas visuais obrigatórios nos campos.
- **Formato de e-mail inválido:** Inserir um texto sem o `@` ou sem o `.com` (ex: `usuario#teste.com`). O sistema deve bloquear o envio e exibir *"E-mail inválido"*.

## 🔒 3. Cenários de Segurança
- **Bloqueio por tentativas repetidas:** Errar a senha 5 vezes seguidas com o mesmo e-mail. O sistema deve bloquear temporariamente a conta ou exibir um Captcha.
- **Ocultação de senha:** O campo de senha deve exibir asteriscos ou bolinhas por padrão. O botão de "olhinho" deve alternar corretamente entre exibir e esconder o texto.
- **Injeção de código (SQL Injection / XSS):** Inserir comandos como `' OR '1'='1` nos campos. O sistema deve tratar o texto apenas como string comum e recusar o login.

## 📱 4. Cenários de Interface e Layout (UI/UX)
- **Navegação via teclado:** Pressionar `Tab` deve mover o foco do e-mail para a senha, depois para o botão "Entrar", e o `Enter` deve disparar o login.
- **Responsividade:** A tela deve alinhar e formatar corretamente em computadores, tablets e celulares (sem botões cortados ou textos sobrepostos).



