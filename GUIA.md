# Guia de instalação e publicação

## 1. Montar o Planner no Notion

1. Crie uma página vazia chamada **Planner IA — Demonstração**. Importe `notion/Planner.md` ou copie seu conteúdo para a página.
2. Na página, importe cada um dos cinco CSVs de `bases/` (menu Importar → CSV, ou Configurações → Importar). Se o Notion criar páginas separadas, organize-as abaixo do painel.
3. Renomeie as bases para **Objetivos**, **Tarefas**, **Rotina**, **Obstáculos** e **Acompanhamento**. Confira os tipos das propriedades conforme o README. Datas usam AAAA-MM-DD; confira se foram interpretadas corretamente. Configure Status com as opções Pendente, Em andamento e Concluída quando aplicável.
4. Em cada base filha, crie uma propriedade Relação chamada **Objetivo**, selecione Objetivos e habilite a relação inversa. Nomeie as inversas Tarefas, Rotina, Obstáculos e Acompanhamento. Vincule todos os registros ao objetivo OBJ-01. O campo Objetivo ID serve como referência de importação; CSV não cria relações novas automaticamente. Opcionalmente, crie a autorrelação Dependência em Tarefas, usando os IDs de dependência.
5. Adicione fórmulas e rollups conforme o README. Configure a cor condicional se disponível. Confira que uma tarefa concluída entre oito gera 12,5% de progresso. A revisão fictícia é de 07/02/2027; a fórmula de alerta usa a data real.
6. No painel, digite `/linked` ou procure por visualização vinculada da base de dados. Adicione as quatro visualizações, escolhendo as bases existentes (não crie cópias independentes). Filtre pelo objetivo e organize conforme o README.

## 2. Instalar as cinco habilidades

No Notion, abra Biblioteca → Skills/Habilidades → nova habilidade, ou a opção de upload de habilidade. Importe individualmente os cinco arquivos `SKILL.md` em `habilidades/`, ou copie o conteúdo para cinco páginas de habilidade e preencha a descrição de cada uma. Substitua os nomes de bases mencionados nas instruções por referências reais usando `@`, escolhendo a base correta. Habilite as habilidades. No chat do Notion Agent, invoque cada uma por `/` seguido do nome e use os cinco pedidos do README. Se quiser evitar duplicação de registros, solicite somente uma proposta, sem gravar dados, durante os testes.

No ChatGPT, a disponibilidade de habilidades nativas depende do plano e das configurações. Se o editor estiver disponível, use os mesmos arquivos de instruções; caso contrário, use os arquivos como prompts reutilizáveis em uma conversa. Os testes textuais já foram incluídos no README; a validação das habilidades instaladas no Notion ainda precisa ocorrer.

## 3. Capturar evidências reais

Use somente a página de demonstração e dados fictícios. Capture a tela do painel com suas quatro áreas e a resposta de pelo menos uma habilidade após executá-la. Idealmente, registre as cinco respostas. No Windows, use Win + Shift + S. Recorte nome, e-mail, outras páginas ou informações da conta. Crie a pasta `imagens` no repositório e salve, por exemplo, `planner.png` e `habilidade.png`. Somente depois de salvar, insira no README:

```markdown
![Painel fictício no Notion](imagens/planner.png)
![Execução de habilidade](imagens/habilidade.png)
```

Atualize as declarações sobre implantação e testes no README somente quando tiver realmente concluído essas etapas. Não publique este guia como evidência de execução nativa; ele é um manual de reprodução.

## 4. Publicar no GitHub

1. Acesse https://github.com/new e entre na sua conta.
2. Use `planner-ia-notion` como nome do repositório, descrição `Assistente de planejamento com IA e Notion`, e visibilidade **Public**. Crie o repositório.
3. Extraia o ZIP. Na página do repositório, utilize Add file → Upload files (ou o link de upload se vazio). Envie o README.md, GUIA.md e as pastas `bases`, `habilidades`, `notion` e `imagens` (quando esta existir), mantendo a estrutura de pastas; alternativamente, use GitHub Desktop para publicar a pasta extraída.
4. Confirme o commit. Abra o repositório em uma janela anônima e verifique se o README aparece e as imagens e links funcionam.
5. Copie o endereço da página principal do repositório, não o link de um arquivo. Envie esse endereço na plataforma do curso.

## Checklist

- [x] Objetivo fictício definido.
- [x] Cinco bases de exemplo e quatro áreas do Planner preparadas.
- [x] Cinco instruções reutilizáveis escritas.
- [x] Cinco demonstrações textuais com ChatGPT documentadas.
- [x] README em Markdown.
- [ ] Planner efetivamente importado e configurado no Notion.
- [ ] Habilidades nativas executadas e resultados conferidos.
- [ ] Prints reais sem dados pessoais anexados e links de imagem verificados.
- [ ] Repositório público criado na conta do aluno e testado sem login.
- [ ] Link da página principal submetido ao curso.
