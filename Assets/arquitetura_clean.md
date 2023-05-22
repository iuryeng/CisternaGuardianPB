
# Arquitetura Clean


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


## Veja aqui um diagram que implementa uma API Rest 


- A API REST geralmente é considerada parte dos Adaptadores de Interface. Esses adaptadores são responsáveis por converter dados de entrada e saída em formatos que o núcleo do aplicativo pode entender. No caso de uma API REST, isso geralmente envolve a conversão de solicitações HTTP e respostas em chamadas de método e dados que o núcleo do aplicativo pode usar.

![image](https://github.com/iuryeng/CisternaGuardianPB/assets/38250160/37e5a4f5-fac8-4cf2-ab16-e78446419e4e)


Neste Projeto: 

![image](http://www.plantuml.com/plantuml/png/jLNDRjGm4BxxAKOzfO9zWQXQ5LegvLJ4pnbDxSdA8h4ZsrcneBmxDiJQ8SGHAzfSDfwV-RxvTiQvzG5T6FjEY07bLpmGNDtR7hMvWXy2uYCxz1uUdnp2pSqx4tGuxVUpBpslG2kemGUdpO5PZUrfpOvAIsqDkY-3iqyTzLZbbnhUps_NDHojLh_I9i5uF6WliTFVKQAzZ8_2W8r9sD5xZu4MlWVTSySa9YR9PqzmXvvyLaMRGAv5IV0czvEvnzWK6jarEMX1aBwH70DLDehQdCc-XYm4C2MW84KHkEc7Be9_97VK2-WT9CWFD5YlWtMdMFln3yFpa2mfnF-y_r2fPMMYcLVz1xLu-0ihTZbXFdDPbvMXMt3O4D7ZyJUXcNZ6Oo6jDkhjgL4LsvlhEVnl7PFrpfhWRDUHYyZdmq8uB2r6NHpTjMok5gzGThFUf2CCb3XNAvqVA2HNiV5yOQbCyvDDlWjNWXVYR7EnvvgMrc4iCSemEbfUtdnQvca_6rvaP2OXqWbsk_tsJLL3F7bHYaa55Wta55w_E0mSOojk6uTPLm9dZFH3FPcGKlYMR8h0K5ZAPbyyJToIKUdx_HC0)

Exemplo de modulos

```cmd
src
└── cooperar
    └── domain
        ├── entities
        │   ├── Obra.java
        │   └── Problema.java
        ├── exceptions
        │   └── ObraNotFoundException.java
        ├── usercases
        │   ├── interfaces
        │   │   └── AdicionarProblemaUseCase.java
        │   └── services
        │       └── AdicionarProblemaUseCaseImpl.java
        └── usercases
            ├── interfaces
            │   └── AdicionarProblemaUseCase.java
            └── services
                └── AdicionarProblemaUseCaseImpl.java


```


## Passos 

1. Definir as entidades:

- Identifique as principais entidades do seu domínio relacionadas à funcionalidade que você está implementando. No caso da funcionalidade de acompanhar o progresso da obra, a entidade principal pode ser "Obra" ou "Progresso".
Defina os atributos e métodos necessários para cada entidade, levando em consideração os requisitos da User Story.

2. Definir os casos de uso (Use Cases):

- Identifique quais são as principais ações que o usuário poderá realizar na funcionalidade de acompanhar o progresso da obra. Por exemplo, "Visualizar o percentual concluído da obra" ou "Ver as datas de início e fim planejadas da obra".
Crie interfaces para os casos de uso, especificando os métodos necessários para cada um.

3. Implementar os serviços (Services):

- Crie classes que implementem as interfaces dos casos de uso.
No caso da funcionalidade de acompanhar o progresso da obra, você terá um serviço responsável por calcular o percentual concluído da obra e outro serviço para recuperar as datas de início e fim planejadas.

4. Implementar os repositórios:

- Crie interfaces para os repositórios que serão responsáveis por lidar com a persistência dos dados, como ObraRepository e ProgressoRepository.
Implemente essas interfaces de acordo com a necessidade do seu projeto. No momento, você pode optar por implementações em memória, mas mantenha a estrutura do repositório separada das demais camadas.

5. Conectar as camadas:

- Faça a conexão entre as camadas da Clean Architecture. Por exemplo, no caso dos casos de uso, eles devem depender das interfaces dos repositórios, mas não devem conhecer as implementações concretas.

6. Testar as funcionalidades:

- Crie testes unitários para cada caso de uso, serviço e repositório.
- Garanta que cada parte da funcionalidade esteja funcionando corretamente.

7. Refatorar, se necessário:

- Se surgirem novos requisitos ou se for preciso fazer melhorias no código, siga um processo de refatoração sistemático.
- Identifique as partes do código que precisam ser alteradas e faça as modificações necessárias.
- Certifique-se de manter os testes atualizados durante o processo de refatoração.
- Essas são etapas gerais que você pode seguir para implementar as funcionalidades usando a Clean Architecture





