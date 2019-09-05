![ufersaTeX2](https://raw.githubusercontent.com/josaiasmoura/ufersatex2/master/figuras/ufersatex2-logo.png)

# O que é?

O **ufersaTeX2** é um projeto baseado no [ueceTeX2] e [abnTeX2] para auxiliar os alunos da Universidade Federal Rural do Semi-árido ([UFERSA]) em seus trabalhos de monografias de graduação.

Embora tenha sido escrito para ser utilizado principalmente pelos alunos de Tecnologia da Informação, a ufersaTeX2 é suficientemente configurável e facilmente adaptável para ser utilizada em praticamente todos os cursos da UFERSA. Espera-se que o projeto seja um modelo de trabalho acadêmico que implemente todas as exigências das normas da ABNT sem a necessidade de se preocupar com o estilo ou formatação do documento.

# Por onde começo?
Para utilizar o ufersaTeX2 você precisa seguir os seguintes passos:

1. Clique [aqui](https://github.com/josaiasmoura/ufersatex2/archive/master.zip) para baixar o projeto
2. Descompacte o arquivo no diretório onde você deseja guardar os arquivos do seu trabalho
3. Crie o seu texto a partir do arquivo ``documento.tex`` distribuído no arquivo baixado. O arquivo possui comentários e é, em certa medida, auto-explicativo.

> Você é iniciante em LaTeX ou em abnTeX2? Clique [aqui](https://github.com/abntex/abntex2/wiki/PorOndeComecar) para acessar a página desenvolvida pela equipe do abnTeX2. Nesta página é possível acessar diversos links sobre o LaTeX e sobre o abnTeX2 como, por exemplo, a história do LaTeX e alguns minicursos desenvolvidos em outras universidades

# Como compilar?

Uma vez que todas as informações foram colocadas no documento, você precisará de um programa para compilar e gerar o PDF do seu trabalho.

### Windows

1. Acesse http://miktex.org/download e baixe a última versão disponível do MiKTeX para o seu computador.

2. Instale o MiKTeX com todas as configurações padrão

3. Acesse a pasta onde você baixou o ufersaTeX2

4. Compile na linha de comando (ou execute o arquivo):

      ./compile.bat

O arquivo ``documento.pdf`` será gerado

> Alerta! Não executar o comando ``compile`` com o arquivo ``documento.pdf`` aberto por algum leitor de pdf, isso causará um erro de bloqueio de escrita.

### Linux (Ubuntu)

1. Instale os seguintes pacotes do Latex na linha de comando:

        sudo apt-get update && sudo apt-get install texlive texlive-latex-extra texlive-lang-portuguese texlive-publishers texlive-science texlive-fonts-recommended texlive-bibtex-extra texlive-generic-extra

2. Acesse a pasta onde você baixou o ufersaTeX2

3. Compile na linha de comando:

      ./compile

O arquivo ``documento.pdf`` será gerado

### OverLeaf

De alguma maneira o OverLeaf não compila se a lista de pacotes e outros não estiver no documento principal.

1. Retire o ``\input{lib/preambulo}`` do ``documento.tex`` e insira todo o conteúdo do preambulo no próprio ``documento.tex`` (no mesmo local da importação do preambulo).


# Dicas
Veja a seguir como inserir alguns elementos no seu texto.

### Como inserir uma Tabela
```tex
\begin{table}[h!]
    \centering
    \Caption{\label{tab:vm-config} Máquinas virtuais utilizadas nos testes}
    \UFERSAtab{}{
        \begin{tabular}{llll}
            \toprule
                Nome & Sistema Operacional & Memória alocada & Cores alocados \\
            \midrule \midrule
                Mininet-VM          & Ubuntu (64-bit)	& 1024MB & 1 core \\
                NetworkEmulatorCore	& Ubuntu (32-bit)	& 2048MB & 2 cores \\
            \bottomrule
        \end{tabular}
    }{
        \Fonte{O Autor, 2018}
    }
\end{table}
```


### Como inserir um Quadro
```tex
\begin{quadro}[h!]
    \centering
    \Caption{\label{qua:label_do_quadro} Legenda do Quadro}
    \UFERSAqua{}{
        \begin{tabular}{|c|c|}
            \hline
            Nome & Idade \\
            \hline
            Maria & 25  \\
            \hline
            João & 30 \\
            \hline
        \end{tabular}
    }{
        \Fonte{Elaborado pelo autor}
    }
\end{quadro}
```

### Como inserir uma figura
```tex
\begin{figure}[h!]
    \centering
    \Caption{\label{fig:figura-1} Legenda da figura 1}
    \UFERSAfig{}{
        \fbox{\includegraphics[width=9cm]{figuras/figura-1}}
    }{
        \Fonte{O Autor, 2018}
    }
\end{figure}
```

### Como inserir uma alínea
```tex
\begin{alineas}
    \item Lorem ipsum dolor sit amet;
    \item Praesent vitae nulla varius;
    \item Praesent quis erat eleifend;
    \item Mauris facilisis odio eu:
    \begin{subalineas}
        \item Integer non lacinia magna;
        \item Proin mattis placerat risus.
    \end{subalineas}
\end{alineas}
```

### Como criar Capítulos
```tex
\chapter{Fundamentação Teórica}
\label{cap:fundamentacao-teorica}
```

### Como criar Seções
```tex
% Seções Secundárias
\section{Objetivo Geral 2}
\label{sec:objetivo-geral-2}

% Seções Terciárias
\subsection{Objetivo Geral 3}
\label{sec:objetivo-geral-3}

% Seções Quaternárias
\subsubsection{Objetivo Geral 4}
\label{sec:objetivo-geral-4}

% Seções Quinárias
\subsubsubsection{Objetivo Geral 5}
\label{sec:objetivo-geral-5}
```

### Como inserir um código fonte como imagem
```tex
\begin{figure}[h!]
    \centering
    \Caption{\label{fig:codigo-exemplo} Exemplo de código Java}
    \UFERSAfig{}{
        \fbox{\begin{minipage}{15cm}
        \lstinputlisting[language=Java]{codigos/exemplo.java}
        \end{minipage}}
    }{
        \Fonte{O Autor, 2018}
    }
\end{figure}
```

# Contribuições

Encontrou algum erro? 😅 [Nos avise por aqui]

Gostaria de contribuir? Nos envie um [PR], por que não? 😆

# Atenção

**Este não é um modelo oficial**, trata-se de customizações do [ueceTeX2] e [abnTeX2] para adequar-se as normas da UFERSA. Feita de forma independente pelo aluno Josaias Moura (contato@josaiasmoura.com), aluno graduando em Engenharia de Software pela UFERSA.

O ufersaTeX2 é fornecido gratuitamente e sem garantias e pode ser redistribuído livremente para fins acadêmicos. O ufersaTeX2 é um produto extra-oficial e não está oficialmente vinculada à UFERSA.

# Agradecimentos

Aos responsáveis pelo [ueceTeX2] e [abnTeX2] pelo magnífico trabalho.

[Por Onde Comecar]:https://code.google.com/p/abntex2/wiki/PorOndeComecar
[abnTeX2]:https://github.com/abntex/abntex2
[ueceTeX2]:https://github.com/thiagodnf/uecetex2
[http://miktex.org/download]:http://miktex.org/download
[UFERSA]:https://ufersa.edu.br/
[PR]:https://github.com/josaiasmoura/ufersatex2/compare
[Nos avise por aqui]:https://github.com/josaiasmoura/ufersatex2/issues/new
