# Comentários Textos:

### Texto 1 Comentário:
A engenharia de software vai além de "simplesmente programar", especialmente no que diz respeito a tempo, escala e trade-offs. 
Os engenheiros de software precisam considerar as mudanças inevitáveis ao longo do tempo em seus códigos, bem como a necessidade de adaptações futuras.
Além disso, devem se preocupar com a escalabilidade e eficiência a longo prazo. Esses profissionais também são responsáveis por tomar decisões complexas e de alto risco,
muitas vezes com base em estimativas incertas e informações imprecisas.

### Texto 2 Comentário:
O texto aborda a distinção entre "programação" e "engenharia de software". Ele sugere que a programação é apenas uma parte do processo de engenharia de software. 
Enquanto a programação envolve a criação de novos softwares, a engenharia de software inclui, além da programação, atividades como desenvolvimento, modificação e manutenção ao longo do tempo.
A ideia principal é que, assim como cubos não são simplesmente quadrados e distância não é o mesmo que velocidade, a engenharia de software vai além da programação. 
O fator tempo adiciona uma dimensão crucial, separando-a da programação pura.

## Comparar requisitos não funcionais 2 técnologias:

### Desempenho: Java vs. Python:
**Java:** Java é uma linguagem compilada para bytecode e executada em uma máquina virtual (JVM), o que a torna significativamente mais rápida que Python para a maioria das aplicações. Seu desempenho é sólido tanto em processamento de CPU quanto em tarefas de I/O, devido à otimização da JVM e seu gerenciamento eficiente de memória (garbage collection). Além disso, Java é uma linguagem fortemente tipada, o que proporciona maior controle sobre a alocação de recursos, resultando em melhor desempenho em sistemas de larga escala.

**Python:** Python, por ser uma linguagem interpretada e dinamicamente tipada, apresenta desempenho inferior em comparação com Java. A execução de código Python é geralmente mais lenta, e ele exige mais memória para executar tarefas semelhantes às de Java. Python é mais adequado para desenvolvimento rápido e prototipagem, mas para aplicações de desempenho intensivo, como sistemas de alta demanda ou de processamento em tempo real, Java costuma ser uma escolha superior. No entanto, bibliotecas otimizadas em Python, como NumPy, podem mitigar algumas dessas limitações.

### Segurança: C vs. JavaScript:
**C:** C, sendo uma linguagem de baixo nível e sem gerenciamento automático de memória, oferece grande controle sobre o hardware, mas também é mais propensa a vulnerabilidades de segurança. Erros de programação em C, como estouro de buffer, manipulação incorreta de ponteiros e falhas na alocação de memória, podem resultar em brechas graves. Além disso, como C não possui um sistema de garbage collection, a prevenção de vazamentos de memória é responsabilidade direta do programador, o que pode introduzir riscos de segurança se não for tratado corretamente.

**JavaScript:** JavaScript, uma linguagem de alto nível e amplamente usada para desenvolvimento web, tem várias ferramentas e padrões modernos para mitigar riscos de segurança, como a política de mesma origem (same-origin policy) e Content Security Policy (CSP) para impedir ataques de Cross-Site Scripting (XSS) e Cross-Site Request Forgery (CSRF). No entanto, JavaScript ainda é vulnerável a ataques, especialmente quando utilizado de forma insegura em aplicações web, onde a segurança depende não só da linguagem, mas também de práticas adequadas de codificação e da infraestrutura subjacente. Por ser interpretado em tempo real nos navegadores, a segurança de JavaScript depende muito da implementação correta em frameworks e do uso seguro de bibliotecas externas.

# 3 exemplos de trade-offs requisitos nao funcionais:

### Desempenho vs. Segurança: 
Ao optar por um sistema mais seguro, pode-se implementar autenticações mais rigorosas.
No entanto, essa medida pode impactar negativamente o tempo de resposta do sistema,comprometendo o desempenho.

### Usabilidade vs. Funcionalidade: 
Para garantir maior acessibilidade e facilidade de uso para um público mais amplo, funcionalidades mais complexas podem ser simplificadas,
ocultadas ou até eliminadas, afetando a riqueza de recursos disponíveis.

### Custo vs. Escalabilidade: 
Um site altamente otimizado pode atrair mais usuários, porém, o aumento na complexidade e na capacidade de suportar um grande volume de acessos
resulta em custos maiores de manutenção e infraestrutura.


