# Testes técnicos

O projeto originalmente em JavaScript foi convertido para TypeScript e seu código e estrutura de pastas foram migrados para uma lógica orientada a objetos. Testes básicos de unidade e integração foram criados com base nesta lógica para fins de aprendizagem.


## Índice

- [Instalação](#instalação)
- [Rotas](#rotas)

## Instalação

```bash
#Clone o repositório

$ git clone https://github.com/thiago-b-coelho/desafio-tech-tests.git

# Vá para o diretório do projeto:

$ cd desafio-tech-tests

#Instala dependências

$ npm instalar

# Construa o projeto (compilar TypeScript)

$ npm executar compilação
```

Para que os testes de integração e solicitações HTTP funcionem você deve criar um banco de dados MySQL em seu computador.
Com o banco de dados criado renomeie o arquivo __.env.example__ para __.env__ e atualize os valores de suas variáveis. Execute o Knex para criar as migrações.

```bash
#Criar migrações

$ npx knex migrar:up
```

Agora você pode iniciar o servidor e executar os dois conjuntos de testes.

```bash
#Inicie o servidor

$ npm início

# Execute os testes de integração

$ npm executar teste:int


# Execute os testes unitários

$ npm executar teste: unidade

# Alternativamente execute todos os testes de uma vez

$ npm executar teste
```

Um dos testes de integração cria um aluno no banco de dados e ele é ignorado por padrão. Você pode mudar isso removendo o __.skip__ na linha 10 (no momento em que este README foi escrito) em [este arquivo](./src/module/aluno/__tests__/aluno.int.spec.ts)

```bash
# antes
it.skip("##POST /aluno deve ser capaz de POST...")

# depois
it("##POST /aluno deve ser capaz de POST...")
```

## Rotas

Com o sistema instalado e funcionando em __http://localhost:3000__, use o software insomnia ou similar para testar as solicitações HTTP para a seguinte rota:

### OBTER / POSTAR
     /aluno

Uma inserção 'aluno' válida é a seguinte:

     {
         "nome": "aluno",
         "cpf": "12345678911",
         "idade": 12
     }

* "nome" deve conter apenas letras e seu comprimento deve ser maior que 1;
* “cpf” deve ter exatamente 11 dígitos e deve ser apenas números;
* "idade" deve ser maior que 2.
​Consulte os detalhes
Enviar feedback
Painéis laterais
Histórico
Salvas
Contribuir