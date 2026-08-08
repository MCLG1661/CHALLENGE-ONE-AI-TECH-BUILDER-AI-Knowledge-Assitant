# AI KNOWLEDGE ASSISTANT

Agente Inteligente, que transforma documentos técnicos em conhecimento estruturado por meio de classificação temática, extração de palavras-chave e técnicas de Inteligência Artificial, lê os arquivos, quebra o conteúdo em trechos, gera embeddings semânticos e indexa tudo com FAISS. Utiliza o modelo **Google Gemini** para responder perguntas com base em um conjunto de documentos pessoais ou corporativos, a partir de uma base de conhecimento **persistente e gerenciável**.

![Python](https://img.shields.io/badge/Python-3.9+-blue?style=for-the-badge&logo=python&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Gemini-1.5%20Flash-8E75B2?style=for-the-badge&logo=google&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-UI-ff69b4?style=for-the-badge&logo=gradio&logoColor=white)
![FAISS](https://img.shields.io/badge/FAISS-Vector%20Search-0052CC?style=for-the-badge)
![Colab](https://img.shields.io/badge/Google%20Colab-Suportado-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![Drive](https://img.shields.io/badge/Google%20Drive-Persistência-4285F4?style=for-the-badge&logo=googledrive&logoColor=white)
![Status](https://img.shields.io/badge/Status-Funcionando-brightgreen?style=for-the-badge)

## 🏆 Desafio

1. Criar um agente de IA
2. Processar documentos (PDF/CSV)
3. Fazer deploy na Oracle Cloud (OCI)

## 📌 Sobre o Projeto

**Agente Inteligente** construído para o **Challenge ONE da Alura**. Ele utiliza o modelo **Gemini** do Google para responder perguntas com base em um conjunto de documentos (PDF, DOCX, TXT, MD). A grande inovação é a **persistência da base de conhecimento**, que é salva no seu Google Drive, permitindo que você mantenha os documentos e o índice FAISS entre diferentes sessões no Google Colab. Capaz de analisar documentos PDF e responder perguntas sobre:

- 📄 **Governança de IA no Setor Público** - Recomendações da Transparência Brasil
- 📘 **Manual de Inteligência Artificial** - Conceitos, ferramentas (Dify, DISC) e modelos de negócio
- 📚 **Inteligência Artificial: Avanços e Tendências** - Publicação da USP sobre IA
- 📊 **Análise de Dados: Da Teoria à Prática** - Conceitos fundamentais de análise de dados

### 🎯 Objetivo

Criar um assistente inteligente que tem uma base de dados e pode ser alimentado com documentos pessoais ou corporativos, fornecendo respostas precisas e contextualizadas, mantendo a base de dados de forma segura e persistente.Facilitando a consulta e análise de documentos complexos sobre Inteligência Artificial, permitindo que usuários obtenham respostas rápidas e precisas em linguagem natural.

## 💡 Solução Proposta

A solução recebe documentos técnicos em PDF (como relatórios de riscos a direitos humanos) e utiliza **técnicas avançadas de Inteligência Artificial** (Google Gemini) para analisar o conteúdo e retornar **informações estruturadas e respostas em linguagem natural**.


## ✨ Funcionalidades e Descrições Técnicas

✅ 📂 **Importação automática do Google Drive** : Aponta para uma pasta e o agente cataloga todos os PDFs, TXTs, MDs e DOCXs nela.

✅ ⬆️ **Upload manual** : Direto pela interface.

✅ 💾 **Base persistente** : Os documentos, trechos e o índice vetorial são salvos no Drive, então nada se perde ao reiniciar o notebook.

✅ 📄 **Classificação Automática de Conteúdos** : Identifica automaticamente seções específicas sobre o tema consultado

✅ 🔑 **Extração de Palavras-Chave** : Extrai termos-chave como "Due Diligence", "Cadeia de Suprimentos" 

✅ 🔗 **Identificação de Conteúdos Relacionados** : Conecta diferentes partes do documento que tratam do mesmo tópico

✅ 🧠 **Organização Inteligente da Base de Conhecimento** : Estrutura as informações para respostas rápidas e precisas

✅ 💾 Possibilidade de exportação da conversa em .txt.


## ❗ Diferencial
Diferente de buscadores tradicionais, o agente **compreende o contexto** e responde em **linguagem natural**, sem que o usuário precise ler documentos extensos.

## 🏗️ Arquitetura da Solução

```
flowchart TD
    A[Documentos PDF, DOCX, TXT, MD] --> B[Extração de Texto]
    B --> C[Divisão em Chunks]
    C --> D[Embeddings com Sentence Transformers]
    D --> E[(FAISS - Indexação Vetorial)]
    F[Pergunta do Usuário] --> G[Embedding da Pergunta]
    G --> E
    E --> H[Busca por Similaridade]
    H --> I[Contexto Recuperado]
    I --> J[Gemini 1.5 Flash]
    J --> K[Resposta com Citação das Fontes]

```

## 🎨 Interface Personalizada
Este agente possui uma interface moderna com : 

- Temas personalizáveis (azul, roxo, verde, laranja, escuro)
- Upload de documentos via interface
- Exemplos de perguntas prontas para uso
- Respostas em linguagem natural baseadas nos documentos

## 🛠️ Tecnologias

- **Google Colab**: Ambiente de desenvolvimento e execução.
- **Google Gemini 1.5 Flash (via `google-genai`)**: Modelo de linguagem para geração de respostas.
- **Gradio 4.0+**: Criação da interface web interativa.
- **Sentence Transformers**: Geração de embeddings para busca semântica.
- **FAISS**: Indexação e busca vetorial de alta performance.
- **PyPDF, python-docx**: Leitura de arquivos PDF, DOCX, TXT e MD.
- **Google Drive**: Armazenamento persistente dos documentos e da base de dados (chunks, metadados e índice).

### ☁️ Infraestrutura e Deploy

**Google Colab** - Ambiente de desenvolvimentoEste agente foi projetado para ser executado no **Google Colab**. Sua base de conhecimento é persistente graças ao **Google Drive**:

- **Arquivos Salvos**: Os documentos e a base de dados (`chunks.pkl`, `metadados.json`, `indice.faiss`) são salvos em `Meu Drive/alura_agente_base/`, garantindo que seu trabalho não seja perdido ao fechar o Colab.
- **Pasta Padrão**: A pasta `Agente_Alura_Documentos` no Drive serve como repositório para novos documentos que serão automaticamente importados.

## ⚙️ Funcionalidades Técnicas

### 📥 Processamento de Documentos
- **Upload de PDFs** via Google Colab
- **Extração automática** de texto com PyPDF2
- **Limpeza e preparação** do texto para análise

### 🧠 Inteligência Artificial
- **Modelo:** Google Gemini 1.0 Pro (via API)
- **Técnica:** RAG (Retrieval-Augmented Generation)
- **Contexto:** Os documentos são usados como base de conhecimento
- **Personalização:** O agente responde APENAS com base no documento fornecido

## 💬 Exemplo de Interação

### 📄 Documento Fornecido
*Análise de Dados da Teoia a Prática*

### ❓ Pergunta do Usuário
*Quais são os principais tipos de análise de dados mencionados e o que é dito sobre recomendações de governança de IA?*

### 🧠 Processamento
1. O agente extrai o texto do documento
2. Busca trechos relevantes sobre riscos trabalhistas
3. Gera uma resposta estruturada

### ✅ Resposta do Agente
*Com base nos documentos fornecidos, apresento as respostas para as duas partes da sua pergunta ....*

## 📁 Estrutura de Pastas

```
📁 CHALLENGE-ONE-AI-TECH-BUILDER-AI-Knowledge-Assitante/
├── 📁 docs/
│   └── 📁 prints/
│       ├── interface_principal.png
│       ├── importacao_drive.png
│       └── exemplo_resposta.png
├── 📁 src/                          (opcional, se quiser modularizar)
│   └── agente.py                    (código principal, se extraído do notebook)
├── 📄 agente.ipynb                  # Notebook principal do Colab
├── 📄 requirements.txt              # Dependências (obrigatório)
├── 📄 .env.example                  # Exemplo de variáveis de ambiente
├── 📄 .gitignore                    # Ignorar arquivos temporários e .env
└── 📄 README.md                     # Documentação completa
```

### 📂 Estrutura Persistente no Google Drive (criada pelo agente)

```
Meu Drive/
├── 📁 Agente_Alura_Documentos/ # Pasta para novos documentos
│ ├── manual.pdf
│ └── relatorio.docx
└── 📁 alura_agente_base/ # Base de dados persistente
├── chunks.pkl # Chunks de texto
├── metadados.json # Metadados dos chunks
├── indice.faiss # Índice FAISS
└── 📁 arquivos/ # Cópia dos arquivos processados
```

## 📁 Estrutura do Projeto

### Repositório GitHub
- `agente.ipynb`: Notebook principal para execução no Google Colab.
- `requirements.txt`: Dependências do projeto.
- `.env.example`: Modelo para variáveis de ambiente (a chave é configurada via Secrets do Colab).
- `docs/prints/`: Prints de tela da interface.
- `README.md`: Documentação completa.

### Google Drive (Criado Automaticamente)
- `Agente_Alura_Documentos/`: Pasta onde você deve colocar seus documentos (PDF, DOCX, TXT, MD). O agente importa automaticamente os arquivos desta pasta.
- `alura_agente_base/`: Base de dados persistente com chunks, metadados e índice FAISS, garantindo que seu trabalho não seja perdido ao fechar o Colab.

## 📸 Prints de Tela

### 📄 Imagem do Agente
![📄 Agente Funcionando](docs/prints/Alura-Agente-Imagem-do-Agente.png)
*📄 Agente Funcionando*

### 💬 Interação com o Agente - Pergunta Respondida 
![💬 Exemplo de Pergunta](docs/prints/Alura-Agente-Imagem-Pergunta-Respondida.png)
*💬 Exemplo de pergunta e 🎯 resposta completa e estruturada ao agente* 

## 🖥️ Interface Gradio

A interface Gradio gera um link público temporário
 
## 🗺️ Roadmap e Melhorias Futuras

### Implementado (Versão Atual)

✅ Extração de texto de PDFs com PyPDF2

✅ Upload de documentos no Google Drive

✅ Persistência da base no Google Drive

✅ Leitura de múltiplos formatos (.pdf, .docx, .txt, .md)

✅ Integração com Google Gemini

✅ Respostas baseadas em documentos

### Melhorias Futuras (Planejado)

#### 🔍 Camada de Recuperação com LangChain

- **Implementar retriever** para buscar os trechos mais relevantes
- **Criar cadeias RAG** (Retrieval-Augmented Generation)
- **Citar fontes** das respostas (transparência)
- **Suporte a múltiplos documentos** em uma única base de conhecimento

#### ⚡ Melhorias de Performance

- **Cache de embeddings** para reutilização
- **Busca híbrida** (semântica + palavras-chave)

#### 🌐 Expansão

- **Interface web** com Streamlit ou Gradio
- **Deploy na OCI** (Oracle Cloud Infrastructure)
- **Suporte a CSV** para dados estruturados
- **Dashboard de análise** de riscos

## 🤝 Como Contribuir

1. Faça um Fork do projeto
2. Crie uma branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## 🙏 Agradecimentos

- Oracle Next Education (ONE) - Pela Oportunidade e Mentoria
 
- OCI - Pela Infraestrutura

- Mentores e Organizadores - Pelo Suporte e Orientação

## 👨‍💻 Autor

**Marcus Guedes**
- LinkedIn: https://www.linkedin.com/in/marcusguedes/
- GitHub: https://github.com/MCLG1661

## ⭐ Projeto desenvolvido como CHALLENGE do ONE AI TECH BUILDER
