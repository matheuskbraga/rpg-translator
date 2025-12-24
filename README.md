# ☢️ Tradutor de PDF RPG (Fallout Edition)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![CustomTkinter](https://img.shields.io/badge/GUI-CustomTkinter-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Functional-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-purple?style=for-the-badge)

Uma ferramenta desenvolvida em Python com interface gráfica moderna (**CustomTkinter**) projetada para auxiliar na tradução de livros de RPG densos (como o _Core Rulebook_ de Fallout) do Inglês para o Português (PT-BR).

O script é otimizado para lidar com arquivos **PDF grandes (+300MB)** sem sobrecarregar a memória RAM, extraindo o texto, traduzindo via API e exportando para um documento Word (`.docx`) organizado por páginas.

## 📋 Funcionalidades

- **Interface Moderna:** GUI construída com `customtkinter` (Dark Mode nativo).
- **Suporte a Arquivos Grandes:** Utiliza `PyMuPDF` (fitz) para processamento eficiente de PDFs pesados (300MB+) via _streaming_ (não carrega tudo na RAM).
- **Multithreading:** O processo de tradução roda em uma _thread_ separada, mantendo a interface responsiva e com barra de progresso em tempo real.
- **Tradução Automatizada:** Integração com a biblioteca `deep-translator` (Google Translate Free API).
- **Anti-Rate Limit:** Sistema de _delay_ inteligente entre requisições para evitar bloqueios de IP durante traduções longas.
- **Saída Organizada:** Gera um arquivo `.docx` mantendo a separação dos textos por cabeçalhos de página, facilitando a leitura paralela.

## 🛠️ Tecnologias Utilizadas

- [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter) - Interface Gráfica moderna baseada em Tkinter.
- [PyMuPDF (Fitz)](https://pymupdf.readthedocs.io/) - Leitura, renderização e extração de dados de PDF de alta performance.
- [Deep Translator](https://github.com/nidhaloff/deep-translator) - Abstração flexível para múltiplas APIs de tradução.
- [Python-Docx](https://python-docx.readthedocs.io/) - Criação e manipulação de arquivos Microsoft Word.

## 🚀 Como Executar

### Pré-requisitos

Certifique-se de ter o [Python 3.x](https://www.python.org/) instalado em sua máquina.

### Instalação

1.  Clone este repositório:

    ```bash
    git clone https://github.com/matheuskbraga/rpg-translator.git
    ```

2.  Instale as dependências necessárias via `pip`:

    ```bash
    pip install customtkinter pymupdf deep-translator python-docx
    ```

3.  Execute o script:
    ```bash
    python tradutor_rpg.py
    ```

## 📖 Como Usar

1.  Ao abrir o programa, clique no botão **"Selecionar Arquivo PDF"**.
2.  Navegue e escolha o arquivo do livro de RPG (ex: `Fallout_RPG_Core_Rulebook.pdf`).
3.  O botão **"Iniciar Tradução"** ficará disponível (verde). Clique nele.
4.  Acompanhe o progresso na barra inferior e no log de eventos (console na interface).
5.  Ao finalizar, um arquivo com o sufixo `_PT-BR.docx` será criado automaticamente na mesma pasta do arquivo PDF original.

## ⚠️ Limitações Conhecidas

- **Perda de Layout:** O script foca exclusivamente na extração e tradução do **conteúdo textual**. Imagens, fundos coloridos, tabelas complexas e a diagramação original do PDF **não** são mantidos no arquivo de saída. O objetivo é criar um texto de apoio (`.docx`) para leitura, não uma réplica visual do livro.
- **Tempo de Execução:** Devido aos limites da API gratuita de tradução, existe um _delay_ programado (0.5s) entre blocos de texto. Traduzir um livro de 400 páginas pode levar de 30 minutos a algumas horas.
- **Terminologia:** A tradução é feita por máquina (Machine Translation). Termos específicos do universo ("Perks", "VATS", "S.P.E.C.I.A.L", "Wasteland") podem ser traduzidos literalmente.

## ⚖️ Aviso Legal (Disclaimer)

Este software é uma ferramenta de automação para fins educacionais, de estudo de programação e acessibilidade pessoal.

- Este projeto **não** contém, distribui ou hospeda nenhum arquivo PDF protegido por direitos autorais.
- O usuário é responsável por possuir a cópia legal do material que deseja traduzir para uso privado.
- **Fallout** é uma marca registrada da **Bethesda Softworks LLC**. Este projeto não tem qualquer afiliação oficial com a Bethesda.

## 🤝 Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma _issue_ para relatar bugs ou enviar um _pull request_ com melhorias no código.

---

Desenvolvido por **[Seu Nome]**
