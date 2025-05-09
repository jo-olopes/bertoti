# Comentários Textos:

### Texto 1:
What precisely do we mean by software engineering? What distinguishes “software engineering” from “programming” or “computer science”? And why would Google have a unique perspective to add to the corpus of previous software engineering literature written over the past 50 years?

The terms “programming” and “software engineering” have been used interchangeably for quite some time in our industry, although each term has a different emphasis and different implications. University students tend to study computer science and get jobs writing code as “programmers.”

“Software engineering,” however, sounds more serious, as if it implies the application of some theoretical knowledge to build something real and precise. Mechanical engineers, civil engineers, aeronautical engineers, and those in other engineering disciplines all practice engineering. They all work in the real world and use the application of their theoretical knowledge to create something real. Software engineers also create “something real,” though it is less tangible than the things other engineers create.

Unlike those more established engineering professions, current software engineering theory or practice is not nearly as rigorous. Aeronautical engineers must follow rigid guidelines and practices, because errors in their calculations can cause real damage; programming, on the whole, has traditionally not followed such rigorous practices. But, as software becomes more integrated into our lives, we must adopt and rely on more rigorous engineering methods. We hope this book helps others see a path toward more reliable software practices
### Comentário Texto 1:
A engenharia de software vai além da programação, aplicando conhecimentos teóricos para construir algo preciso e real, similar a outras engenharias. Embora menos rigorosa que as engenharias tradicionais, a engenharia de software precisa se tornar mais estruturada, especialmente com a crescente importância do software em nossas vidas. O livro busca promover práticas mais confiáveis nessa área.


### Texto 2:
Programming Over Time We propose that “software engineering” encompasses not just the act of writing code, but all of the tools and processes an organization uses to build and maintain that code over time. What practices can a software organization introduce that will best keep its code valuable over the long term? How can engineers make a codebase more sustainable and the software engineering discipline itself more rigorous? We don’t have fundamental answers to these questions, but we hope that Google’s collective experience over the past two decades illuminates possible paths toward finding those answers.

One key insight we share in this book is that software engineering can be thought of as “programming integrated over time.” What practices can we introduce to our code to make it sustainable—able to react to necessary change—over its life cycle, from conception to introduction to maintenance to deprecation?

The book emphasizes three fundamental principles that we feel software organizations should keep in mind when designing, architecting, and writing their code:

Time and Change How code will need to adapt over the length of its life

Scale and Growth How an organization will need to adapt as it evolves

Trade-offs and Costs How an organization makes decisions, based on the lessons of Time and Change and Scale and Growth
### Comentário Texto 2:
A engenharia de software envolve não apenas a escrita de código, mas também as práticas e processos para manter o código sustentável ao longo do tempo. O livro destaca três princípios fundamentais: adaptação do código às mudanças, a evolução da organização à medida que cresce e a tomada de decisões com base nessas mudanças e no crescimento.


## Resumo do slide 57:

Na entrega de um produto ou código, o foco deve ser garantir a funcionalidade essencial. Uma versão simples e eficaz facilita a validação, permite aprimoramentos rápidos e promove a evolução contínua do sistema.


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

# Atividade 5:


### Classe Produto:
```
package loja;

public class Produto {
    
    private String nome;
    private String categoria;
    private double preco;
    
    public Produto(String nome, String categoria, double preco) {
        this.nome = nome;
        this.categoria = categoria;
        this.preco = preco;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getCategoria() {
        return categoria;
    }

    public void setCategoria(String categoria) {
        this.categoria = categoria;
    }

    public double getPreco() {
        return preco;
    }

    public void setPreco(double preco) {
        this.preco = preco;
    }

    @Override
    public String toString() {
        return "Produto [nome=" + nome + ", categoria=" + categoria + ", preco=" + preco + "]";
    }
}
```
### Classe Loja:
```
package loja;

import java.util.List;
import java.util.LinkedList;

public class Loja {
    
    private List<Produto> produtos = new LinkedList<Produto>();

    public void adicionarProduto(Produto produto) {
        produtos.add(produto);
    }

    public Produto buscarProdutoPorNome(String nome) {
        for (Produto produto : produtos) {
            if (produto.getNome().equalsIgnoreCase(nome)) {
                return produto;
            }
        }
        return null;
    }

    public List<Produto> buscarProdutosPorCategoria(String categoria) {
        List<Produto> encontrados = new LinkedList<Produto>();
        for (Produto produto : produtos) {
            if (produto.getCategoria().equalsIgnoreCase(categoria)) {
                encontrados.add(produto);
            }
        }
        return encontrados;
    }

    public List<Produto> buscarProdutosPorPreco(double preco) {
        List<Produto> encontrados = new LinkedList<Produto>();
        for (Produto produto : produtos) {
            if (produto.getPreco() <= preco) {
                encontrados.add(produto);
            }
        }
        return encontrados;
    }

    public List<Produto> getProdutos() {
        return produtos;
    }
}
```
### Classe TesteLoja:
```
package loja;

import static org.junit.jupiter.api.Assertions.*;

import org.junit.jupiter.api.Test;

import java.util.List;

class TesteLoja {

    @Test
    void test() {

        Loja loja = new Loja();
        loja.adicionarProduto(new Produto("Camiseta", "Roupas", 29.90));
        loja.adicionarProduto(new Produto("Calça Jeans", "Roupas", 79.90));
        loja.adicionarProduto(new Produto("Tênis Esportivo", "Calçados", 120.00));

        assertEquals(loja.getProdutos().size(), 3);

        Produto produto = loja.buscarProdutoPorNome("Camiseta");
        assertNotNull(produto);
        assertEquals(produto.getPreco(), 29.90);


        List<Produto> produtosRoupas = loja.buscarProdutosPorCategoria("Roupas");
        assertEquals(produtosRoupas.size(), 2);
        assertEquals(produtosRoupas.get(0).getCategoria(), "Roupas");

        List<Produto> produtosBaratos = loja.buscarProdutosPorPreco(50.00);
        assertEquals(produtosBaratos.size(), 2); // Deve retornar a Camiseta e a Calça Jeans
    }
}
```

