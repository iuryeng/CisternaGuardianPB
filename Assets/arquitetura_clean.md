![image](https://github.com/iuryeng/CisternaGuardianPB/assets/38250160/02004395-27b5-488f-9657-44a4faa23c35)


Neste Projeto: 

```plantUML

@startuml

package "Domain" {
    class Obra <<Entity>> {
        + id : string
        + nome : string
        + adicionar_problema(problema: Problema): void
    }

    class Fiscalizacao <<Entity>> {
        + id : string
        + dataInicio : Date
        + dataFim : Date
    }
}

package "Use Cases" {
    interface AdicionarProblemaUseCase <<Interface>> {
        + execute(obraId : string, problema : Problema) : void
    }

    class AdicionarProblemaUseCaseImpl <<Service>> {
        - obraRepository : ObraRepository
        + execute(obraId : string, problema : Problema) : void
    }

    interface AdicionarFiscalizacaoUseCase <<Interface>> {
        + execute(obraId : string, fiscalizacao : Fiscalizacao) : void
    }

    class AdicionarFiscalizacaoUseCaseImpl <<Service>> {
        - obraRepository : ObraRepository
        + execute(obraId : string, fiscalizacao : Fiscalizacao) : void
    }
}

package "Interfaces" {
    interface ObraRepository <<Interface>> {
        + save(obra : Obra) : void
        + findById(id : string) : Obra
    }
}

package "Infrastructure" {
    class ObraRepositoryImpl <<Repository>> {
        + save(obra : Obra) : void
        + findById(id : string) : Obra
    }
}

Obra --> AdicionarProblemaUseCaseImpl : Uses
AdicionarProblemaUseCase --> ObraRepository : Uses
Obra --> AdicionarFiscalizacaoUseCaseImpl : Uses
AdicionarFiscalizacaoUseCase --> ObraRepository : Uses
ObraRepository --> ObraRepositoryImpl : Implements

@enduml




```



![jPJHJi8m58RlznGdN46K5rW8GKMINM4qNfj3TqOQjtPfEo8QtjrMswmsWs2KtR2Uy_Vy7p-b2srGcQwfiwn5zefRWj5IDiZ523uoi0-hKMjORnJ2R7Ol33Vx-Tpr_7C5l8GSj55SRAEga0qDrR7aZ4k1wgLLSbDJW-FmaiE3Vvlai9Ey_Dfso2AE5TSCQ_wE3ENlU4](https://github.com/iuryeng/CisternaGuardianPB/assets/38250160/8481d9a2-6a7d-4e9e-8e78-2d739f586a06)

## Clean Architecture

conjunto de princípios de design que visa tornar os sistemas de software mais compreensíveis, flexíveis e sustentáveis

1. **Separação de preocupações**: A arquitetura limpa separa as responsabilidades em diferentes camadas. No diagrama, você pode ver que temos quatro pacotes principais: Domain, Use Cases, Interfaces e Infrastructure. Cada um deles tem uma responsabilidade específica.

2. **Domain**: Contém as entidades do domínio de negócios (neste caso, Obra e Fiscalizacao). As entidades são os objetos centrais do seu sistema e encapsulam a lógica de negócios que não muda com frequência.

3. **Use Cases**: Define os casos de uso do sistema. Cada caso de uso é uma operação específica que o sistema pode realizar. Neste caso, temos dois casos de uso: AdicionarProblema e AdicionarFiscalizacao.

4. **Interfaces**: Define as interfaces que os repositórios devem implementar. Os repositórios são responsáveis por lidar com a persistência de dados (por exemplo, salvar e recuperar entidades do banco de dados).

5. **Infrastructur**e: Implementa as interfaces definidas no pacote de Interfaces. Esta camada contém detalhes específicos de tecnologia que não devem influenciar as camadas superiores.

6. **Princípio da inversão de dependência**: As camadas de alto nível não devem depender de camadas de baixo nível. Ambas devem depender de abstrações. No diagrama, você pode ver que o caso de uso AdicionarProblemaUseCaseImpl depende da interface ObraRepository, não da implementação concreta ObraRepositoryImpl. Isso significa que você pode mudar a implementação do repositório sem afetar o caso de uso.

7. **Princípio de responsabilidade única**: Cada classe tem uma única responsabilidade. Por exemplo, a classe Obra é responsável apenas por manter o estado de uma obra e possivelmente algumas regras de negócios relacionadas a obras. Da mesma forma, a classe AdicionarProblemaUseCaseImpl é responsável apenas por adicionar um problema a uma obra.

8. **Princípio Aberto/Fechado**: As entidades e casos de uso são abertos para extensão, mas fechados para modificação. Isso significa que você pode adicionar novos comportamentos sem alterar o código existente. Por exemplo, você pode adicionar um novo caso de uso sem alterar as classes de entidade ou outros casos de uso.

9. **Princípio de substituição de Liskov**: As classes concretas podem ser substituídas por suas interfaces. Por exemplo, você pode substituir a implementação concreta do ObraRepository (ObraRepositoryImpl) por qualquer outra classe que implemente a interface ObraRepository.



