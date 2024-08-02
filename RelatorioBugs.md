# Relatório de Bugs

## Resumo
Este relatório documenta os bugs encontrados durante os testes da nova feature do módulo de curso.

## Metodoligia
O relatório gerado e escrito em Markdown foi a forma mais simples e prática para acompanhar o padrão do README e relatar os bugs encontrados.

## Bugs Encontrados

### Bug 1: Cadastro - Campos em branco
- **Descrição**: Bug que envolve os CT003 e CT004. Foi possível cadastrar cursos tendo ao menos um campo em branco ou tendo todos os campos em branco. O fluxo não possui qualquer validação para garantir campos obrigatórios ou o seu devido preenchimento.
- **Passos para Reproduzir**:
1. Navegar para a página de cadastro de cursos.
2. Preencher o campo "Nome do curso" ou deixar em branco.
3. Preencher o campo "Descrição do Curso" ou deixar em branco.
4. Preencher o campo "Instrutor" ou deixar em branco.
5. Preencher o campo "Url da imagem de capa" ou deixar em branco.
6. Preencher os campos "Data de início" e "Data de fim" ou deixar em branco.
7. Preencher o campo "Número de vagas" ou deixar em branco.
8. Escolher uma opção em "Tipo de curso" ou deixar em branco.
9. Clicar no botão Cadastrar Curso.
- **Resultado Esperado**: O usuário deve ver uma mensagem impedindo o cadastro do curso ou deve ver um destaque em campos que devem ser preenchidos.
- **Resultado Atual**: Não há qualquer mensagem ou validação de campos em branco. O curso acaba sendo cadastrado com informações não preenchidas.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Alta
- **Prioridade**: Alta
- **Status**: Aberto

### Bug 2: Cadastro - Intervalo de datas
- **Descrição**: Bug que envolve o CT005. Foi possível inserir datas onde o intervalo da data de fim é menor que a data de início.
- **Passos para Reproduzir**:
1. Navegar para a página de cadastro de cursos.
2. Preencher o campo "Nome do Curso".
3. Preencher o campo "Descrição do Curso".
4. Preencher o campo "Instrutor".
5. Preencher o campo "Url da imagem de capa".
6. Preencher o campo "Data de início" com 01/01/2025 e "Data de fim" com 20/02/2024.
7. Preencher o campo "Número de vagas".
8. Escolher uma opção em "Tipo de curso".
9. Clicar no botão Cadastrar Curso.
- **Resultado Esperado**: O usuário deve ver uma mensagem impedindo o cadastro do curso ou deve ver um destaque nos campos de data indicando que a data de fim deve ser maior que a data de início.
- **Resultado Atual**: Não há qualquer mensagem ou validação ao intervalo de datas informado.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Alta
- **Prioridade**: Alta
- **Status**: Aberto

### Bug 3: Cadastro - Vagas zeradas
- **Descrição**: Bug que envolve o CT006. Foi possível cadastrar cursos com número de vagas zeradas. O fluxo não possui qualquer validação de quantidade mínima de vagas.
- **Passos para Reproduzir**:
1. Navegar para a página de cadastro de cursos.
2. Preencher o campo "Nome do Curso".
3. Preencher o campo "Descrição do Curso".
4. Preencher o campo "Instrutor".
5. Preencher o campo "Url da imagem de capa".
6. Preencher os campos "Data de início" e "Data de fim".
7. Preencher o campo "Número de vagas" com 0.
8. Escolher uma opção em "Tipo de curso".
9. Clicar no botão Cadastrar Curso.
- **Resultado Esperado**: O usuário deve ver uma mensagem impedindo o cadastro do curso ou deve ver um destaque no campo de vagas impedindo que seja feito o cadastro com o valor 0.
- **Resultado Atual**: Não há qualquer mensagem ou validação com o número 0 de vagas. O curso acaba sendo cadastrado dessa forma.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Alta
- **Prioridade**: Média
- **Status**: Aberto

### Bug 4: Cadastro - Vagas negativas
- **Descrição**: Bug que envolve o CT007. Foi possível cadastrar cursos com número de vagas negativas. O fluxo não possui qualquer validação para evitar uma quantidade negativa de vagas.
- **Passos para Reproduzir**:
1. Navegar para a página de cadastro de cursos.
2. Preencher o campo "Nome do Curso".
3. Preencher o campo "Descrição do Curso".
4. Preencher o campo "Instrutor".
5. Preencher o campo "Url da imagem de capa".
6. Preencher os campos "Data de início" e "Data de fim".
7. Preencher o campo "Número de vagas" com -5.
8. Escolher uma opção em "Tipo de curso".
9. Clicar no botão Cadastrar Curso.
- **Resultado Esperado**: O usuário deve ver uma mensagem impedindo o cadastro do curso ou deve ver um destaque no campo de vagas impedindo que seja feito o cadastro com um valor menor que 0.
- **Resultado Atual**: Não há qualquer mensagem ou validação com o número negativo de vagas. O curso acaba sendo cadastrado dessa forma.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Alta
- **Prioridade**: Média
- **Status**: Aberto

### Bug 5: Validação de caracteres - Números em campos de letras
- **Descrição**: Bug que envolve o CT008. Foi possível preencher com números os campos que deveriam aceitar apenas letras.
- **Passos para Reproduzir**:
1. Navegar para a página de cadastro de cursos.
2. Preencher o campo "Nome do curso" com números.
3. Preencher o campo "Instrutor" com números.
- **Resultado Esperado**: Números não devem ser aceitos nos campos destacados.
- **Resultado Atual**: Não há qualquer impedimento para preencher os campos com números. O curso acaba sendo cadastrado com informações incorretas.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Média
- **Prioridade**: Média
- **Status**: Aberto

### Bug 6: Validação de caracteres - Números em campos de letras
- **Descrição**: Bug que envolve o CT009. Foi possível cadastrar cursos sem validar a url de imagem. O curso cadastrado é apresentado como se nenhuma imagem fosse definida.
- **Passos para Reproduzir**:
1. Navegar para a página de cadastro de cursos.
2. Preencher o campo "Url da imagem de capa" com um link que não existe.
3. Clicar no botão Cadastrar Curso.
- **Resultado Esperado**: Qualquer url não existente não deve ser utilizada.
- **Resultado Atual**: Não há qualquer mensagem ou validação com a url da imagem. O curso acaba sendo cadastrado dessa forma.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Baixa
- **Prioridade**: Baixa
- **Status**: Aberto

### Bug 7: Validação de caracteres - Letras em campos de números
- **Descrição**: Bug que envolve o CT010. Foi possível preencher com letras o campo "Número de vagas" que deveria aceitar apenas números.
- **Passos para Reproduzir**:
1. Navegar para a página de cadastro de cursos.
2. Preencher o campo "Número de vagas" com letras.
- **Resultado Esperado**: Letras não devem ser aceitas no campo destacado.
- **Resultado Atual**: Letras não são aceitas, exceto pela letra "e". Por algum motivo acaba sendo a única letra que pode ser utilizada no campo de vagas.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Baixa
- **Prioridade**: Baixa
- **Status**: Aberto

### Bug 8: Exclusão de curso
- **Descrição**: Bug que envolve o CT011. Foi possível verificar que nenhum curso é excluído mesmo após clicar no botão e visualizar a mensagem de confirmação.
- **Passos para Reproduzir**:
1. Navegar para a página de Lista de cursos.
2. Clicar na opção Excluir curso dentre os cursos disponíveis.
- **Resultado Esperado**: O usuário deve visualizar a mensagem de confirmação de exclusão do curso. O curso deve ser excluído. O curso não deve mais aparecer na lista de cursos.
- **Resultado Atual**: A mensagem de confirmação de exclusão é apresentada. O curso não é excluído e permanece na lista de cursos.
- **Ambiente de Teste**: Sistema Operacional: Windows 11 Navegador: Google Chrome Versão 127.0.6533.89 (Compilação oficial) (64 bits)
- **Severidade**: Alta
- **Prioridade**: Alta
- **Status**: Aberto
