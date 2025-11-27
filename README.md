Coleção de fluxos de trabalho do agente de IA n8n RAG
Visão geral
Este repositório contém uma coleção abrangente de fluxos de trabalho n8n que implementam a Geração Aumentada por Recuperação (RAG) para a criação de automação de fluxos de trabalho com inteligência artificial. O repositório serve como uma implementação de referência e uma solução pronta para implantação para geração de fluxos de trabalho n8n. A maioria desses fluxos de trabalho foi extraída do modelo oficial do n8n, do Gumroad ou foi criada pelos próprios usuários.

Estrutura do Repositório
.
├── documentation-for-RAG/        # Documentation datasets for RAG systems
│   └── n8n_documentation_index/  # Indexed n8n documentation
├── n8n.io-templates/ # Reference workflow templates
├── n8n-blog-maker/              # Blog generation workflow system
├── Real Case Example (Credit to @imgroup)/ # Production-ready workflow implementations
├── Categorized/                 # Categorized workflow examples from various source
├── *.json                       # Individual workflow files
└── *.pdf, *.py                  # Utility files and guides
Componentes técnicos
Corpus de Documentação de Fluxo de Trabalho
O repositório inclui um conjunto completo de documentação n8n extraído usando crawl4ai, fornecendo:

Documentação do nó com especificações de parâmetros
Detalhes da execução do fluxo de trabalho
Requisitos de configuração de integração
Padrões e melhores práticas para tratamento de erros
Implementação RAG
O sistema RAG é implementado com os seguintes componentes:

Integração com Banco de Dados Vector : Compatível com Qdrant, Pinecone e Supabase Vector.
Modelos de incorporação : Suporta incorporações OpenAI, Cohere e Jina.
Mecanismos de recuperação : Implementa busca semântica com limites de relevância personalizáveis.
Montagem de Contexto : Construção dinâmica de prompts com fragmentos de documentação recuperados
Geração : Compatível com vários fornecedores de LLM (OpenAI, Anthropic, Google, etc.)
Pontos de integração da API
Pontos de extremidade de webhook para gatilhos externos
Nós de requisição HTTP para comunicação com serviços externos
Conectores de banco de dados (PostgreSQL, MongoDB, MySQL)
Integrações de armazenamento de arquivos (S3, Google Drive, Local)
Categorias de fluxo de trabalho
Categoria	Contar	Descrição
Geração de conteúdo	35+	Fluxos de trabalho automatizados para criação de conteúdo
Interação com o cliente	25+	CRM e automação de atendimento ao cliente
Processamento de dados	20+	Pipelines de ETL e transformação de dados
Produção de mídia	15+	Fluxos de trabalho para geração de vídeo e imagem
Variado	5+	Fluxos de trabalho utilitários e especializados
Credenciais da API
As seguintes credenciais são necessárias para o pleno funcionamento:

Chave de API OpenAI ou provedor LLM equivalente
Credenciais da API do banco de dados Vector
Chaves de API específicas para cada serviço (YouTube, Twitter, etc., conforme necessário)
Configuração
Configure as variáveis ​​de ambiente na sua instância do n8n:

N8N_ENCRYPTION_KEY=your-encryption-key
N8N_VECTOR_DB_URL=your-vector-db-url
N8N_LLM_API_KEY=your-llm-api-key
Configure coleções de banco de dados vetoriais:

N8N_DOC_COLLECTION=n8n_documentation
N8N_WORKFLOW_COLLECTION=workflow_examples
Instale as dependências adicionais, se necessário, para fluxos de trabalho específicos.

Execução
Os fluxos de trabalho podem ser executados através de:

Acionadores de webhook
Execuções agendadas
Ativação manual
Chamadas de API para endpoints n8n
Considerações sobre o desempenho
As consultas RAG geralmente são concluídas em 2 a 5 segundos, dependendo da complexidade.
A geração do fluxo de trabalho pode levar de 10 a 30 segundos para implementações complexas.
Considere o processamento em lotes para operações de alto volume.
