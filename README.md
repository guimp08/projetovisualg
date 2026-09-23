// Para visualização do projeto, deve ser importado todo o código para o visualg na linguagem Portugol
algoritmo "Acesso PRado BANK"

var
  // Variaveis
  login, sucesso: caracter
  senha, opcao: inteiro
  deposito,saldo, saque: real
  logado: logico
  sistema: logico
inicio
  // Atribuições---
  sucesso <- "Login bem sucedido!"
  saldo <- 0
  // Sistema de Login(Infinito)---
  sistema <- verdadeiro
  logado <- falso
  enquanto (sistema = verdadeiro) e (logado= falso) faca
    escreval("---PRadoBANK---")
    escreval("DIGITE SEU LOGIN: ")
    leia(login)
    escreval(login)
    escreval("DIGITE SUA SENHA: ")
    LEIA(senha)
    escreval(senha)
    // Verificação de *login* e *senha*---
    SE ((LOGIN = "Guilherme Prado") e (senha= 170308)) ou ((login= "ADMIN") e (senha=123)) entao
      limpatela
      escreval(sucesso)
      escreval("Seja Bem-Vindo, ",login"!")
      escreval("")
      sistema <- falso
      logado <- verdadeiro //Quebra de login(Infinito)---
      // Para Login incorreto---
    senao
      limpatela
      escreval("Login ou senha incorreto(s). Tente Novamente.")
    fimse
  fimenquanto
  // Portas do MENU---
  enquanto (logado = verdadeiro) e (sistema = falso) faca
    escreval("---MENU---")
    escreval("1-Depósito 2-Saque")
    escreval("3-Saldo 4- Sair")
    leia(opcao)
    escolha opcao
      // Traços opção 1
    caso 1
      limpatela
      escreva("Digite o valor: R$")
      leia(deposito)
      escreval(deposito)
      saldo <- saldo+deposito
      escreval("Foram depositados R$",deposito," em sua conta bancária!")
      escreval("")
      // Traços opção 2
    caso 2
      limpatela
      escreva("Digite o valor do saque: R$")
      leia(saque)
      escreval(saque)
      // Condição opção 2
      se saque <= saldo entao
        saldo <- saldo - saque
        escreval("Foram retirados R$",saque," da sua conta")
      senao
        limpatela
        escreval("Saque não realizado. Motivo: Saldo insulficiente.")
      fimse
      // traço opção 3
    caso 3
      limpatela
      escreval("Seu saldo é de: R$",saldo)
      escreval("")
      // Traço opção 4
    caso 4
      limpatela
      escreval("Saindo do sistema...")
      logado <- falso
      // Outro caso = "ErroR404"
    outrocaso
      limpatela
      escreval("Opção Inválida.")
      escreval("")
      sistema <- falso
  fimescolha
fimenquanto
fimalgoritmo
