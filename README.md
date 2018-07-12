# PacktPub Grabber

Reinvindique [eBook Gratuito de Aprendizagem de hoje da PacktPub] (https://www.packtpub.com/packt/offers/free-learning) e receba notificação via e-mail.

## Dependências

```sh
instalação pip -r requirements.txt
```
Ou, no Arch Linux:
```sh
instalação de pip2 -r requirements.txt
```
## Configuration
Etapas para configurar o script.

#### Informações da conta do PacktPub
Substitua USERNAME e PASSWORD na linha 8 e 9 pelo nome de usuário (endereço de e-mail) e senha do PacktPub.

`` `python
    br.form ["email"] = "USERNAME"
    br.form ["password"] = "SENHA"
`` `

#### Informações da conta de e-mail

O script envia o email de um endereço do Gmail que você especifica para o seu outro endereço de email. Observe que somente a conta do Gmail é aceita para enviar e-mails. Eu aconselho não usar sua conta do Gmail já que você precisa ativar o acesso a aplicativos menos seguros.

* Crie uma nova conta do Gmail.
* [Ativar acesso para aplicativos menos seguros] (https://support.google.com/accounts/answer/6010255?hl=pt-BR) na (nova) conta de envio do Gmail.
* Substitua o "FROM", "TO", e "EMAIL PASSWORD" na última linha com o seu endereço de envio do Gmail, recebendo endereço de e-mail e a senha da conta de envio do Gmail, respectivamente.

```python
    send_email ("FROM", "TO", "PacktPub Grabber", resultado, "EMAIL PASSWORD")
```
Após cada execução, você receberá um e-mail no endereço "TO" com a mensagem de sucesso / falha.

! [Email do PacktPub Grabber] (https://cloud.githubusercontent.com/assets/5013296/17832328/c5f7f45c-671f-11e6-986f-cd78133329d4.png)

## Executar
Duas maneiras de executar o script.

#### Manualmente
Para executar manualmente, basta ir ao shell e digitar:

```python
    python /path/to/packtpub-grabber/packtpub-grabber.py
```
#### Automaticamente
Como o objetivo do script é automatizar todo o processo de obtenção de um Ebook gratuito todos os dias, você deve escolher uma forma automatizada. Portanto, coloque o script em seu VPS e, em seguida, configure uma tarefa cron para que o script seja executado todos os dias no horário determinado.

Execute _crontab -e_ e adicione as seguintes linhas para executar o script everday às 18: 30h.

```
30 6 * * * python /path/to/packtpub-grabber/packtpub-grabber.py 2 >> errors.log
```

Os erros, se houver, podem ser visualizados no arquivo errors.log.
