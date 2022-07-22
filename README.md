# Exercícios do dia 25.1
_Clique [aqui](https://github.com/JonathanRei5/trybe-exercicios/tree/main/modulo-03-desenvolvimento-back-end/bloco-25-deployment/dia-01-infraestrutura-deploy-com-heroku) para ir para o repositório de exercícios._

Link para a aplicação de produção https://heroku-express-jra-prod.herokuapp.com/

Link para a aplicação de homologação https://heroku-express-jra-homolog.herokuapp.com/

### Comandos utilizados:

Cria um _app_ Heroku
```bash
heroku create heroku-express-jra --remote heroku-express
```

renomeia o _remote_ `heroku-express` para `homolog`
```bash
git remote rename heroku-express homolog
```

renomeia o _app_ `heroku-express-jra` para `heroku-express-jra-homolog`
```bash
heroku apps:rename heroku-express-jra-homolog
```

Cria outro _app_ Heroku
```bash
heroku create heroku-express-jra-prod --remote prod
```

Configura as variáveis de ambiente
```bash
heroku config:set RESPONSE_MESSAGE="Olá, esse é um ambiente de homologação\!" --app heroku-express-jra-homolog
```
```bash
heroku config:set RESPONSE_MESSAGE="Olá, esse é um ambiente de produção\!" --app heroku-express-jra-prod
```

Faz _deploy_ do _app_ de homologação
```bash
git push homolog
```

Faz _deploy_ do _app_ de produção
```bash
git push prod
```

### Esses exercícios foram feitos por [min](https://www.linkedin.com/in/jonathanrei5/) na [Trybe](https://www.betrybe.com/)
