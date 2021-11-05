---
title: Padrão Consulta
description: Padrão de Consulta Para Comunicação com a API
---
--8<-- "includes/abbreviations.md"

!!! warning "Documentação destinada para desenvolvedores"

Padrão das consultas entre o aplicativo e o servidor, é necessário para operações como filtro, ordenação e agrupamento do lado do aplicativo assim todas as operações são aplicadas no servidor de forma segura e sem transição de dados desnecessários.

## Classes

As propriedades que tiver `?` após a definição do tipo indica que ela é opicional.

### LoadOptions

Este objeto é usado para especificar as configurações de acordo com as quais o servidor deve processar os dados. Essas configurações são passadas como um parâmetro para o servidor para realizar operações como paginação, filtragem, classificação, etc.

```DART linenums="1"
class LoadOptions {
  int? skip; // (1)

  int? take; // (2)

  List<SortingInfo>? sort; // (3)

  List<Object?>? filter;  // (4)

  List<ExpandInfo>? expand; // (5)

  List<GroupingInfo>? group; // (6)

  List<AggregatorField>? aggregators; // (7)
}
```

1. O número de objetos de dados a serem ignorados desde o início do conjunto resultante.
2. O número de objetos de dados a serem carregados.
3. Uma expressão de classificação. [SortingInfo](#sortinginfo).
4. Uma expressão de filtro.

    Os operadores disponíveis são: `=`, `<>`, `>`, `>=`, `<`, `<=`, `startswith`, `endswith`, `contains`, `notcontains`, `substring` e `in`.

    <h2>Exemplos</h2>

    Exemplos de utilização do fitro com operadores.

    <h3>Filtro binário</h3>
    ```DART
    final filter = ['fieldOne', '=', 1];
    ```

    <h3>Filtro unário</h3>
    ```DART
    final filter = ['!', ['fieldOne', '=', 1] ];
    ```

    <h3>Filtro complexo</h3>
    ```DART
    final filter = [
      [ 'fieldOne', '=', 8 ],
      'and',
      [
        [ 'fieldTwo', '<', 3 ],
        'or',
        [ 'fieldTwo', '>', 11 ]
      ]
    ];
    ```

    <h3>Filtro com substring</h3>

    `[ fieldName, 'substring', position, length, valueCompare ]`

    ```DART
    final filter = [ 'fieldName', 'substring', 1, 1, 'T' ];
    ```

    <h3>Filtro com in</h3>

    ```DART
    final filter = [ 'fieldName', 'in', [1, 2, 3, 4] ];
    ```

5. Uma expressão de expansão, utilizado para expandir os filhos de cada item. [ExpandInfo](#expandinfo).
6. Uma expressão de grupo, utilizado para agrupar o resultado. [GroupingInfo](#groupinginfo).
7. Agregadores para os campos da select, utilizado para aplicar operação de agregação na coluna no agrupamento. [AggregatorField](#aggregatorfield).

!!! warning "Se for informado um `group`, os campos de dados que não tiverem um `aggregators` definido será retornado o primeiro item do grupo."

### SortingInfo

Representa um parâmetro de classificação dos dados.

```DART linenums="1"
class SortingInfo {
  String selector; // (1)

  bool desc; // (2)
}
```

1. Nome do campo de dados a ser usado para classificação.
2. Um sinalizador que indica se os dados devem ser classificados em ordem decrescente. O valor padrão é `true`.

### ExpandInfo

Representa uma definição da expansão de cada item retornado.

```DART linenums="1"
class ExpandInfo {
  String selector; // (1)

  List<ExpandInfo>? expand; // (2)

  List<Object>? filter; // (3)

  List<String>? select; // (4)

  List<SortingInfo>? sort; // (5)

  List<String>? notSelect; // (6)
}
```

1. Nome do campo de dados a ser usado para expandir.
2. Uma expressão de expansão para expandir mais um nível, levando em consideração os dados desse nível. [ExpandInfo](#expandinfo).
3. Uma expressão de filtro que será aplicado sobre os registros a serem expandidos.
4. Nome das colunas que vão ser retornadas, se não estiver preenchidas retornar todas.
5. Uma expressão de classificação. [SortingInfo](#sortinginfo).
6. Nome das colunas que não devem ser retornadas, retornam todas menos as que forem definidas aqui, essa tem prioridade sobre o select.

#### AggregatorField

Representa uma definição de operação a ser aplicada a cada coluna durante o agrupamento.

```DART linenums="1"
class AggregatorField {

  String type; // (1)

  String selector; // (2)

  String groupSeparator; // (3)
}
```

1. Representa o tipo de operação que vai ser aplicada no campo de dados definido no `selector`, podendo ser `sum`, `min`, `max`, `avg`, `count`, `concat`.
2. Nome do campo de dados que vai ser aplicado a operação.
3. Defini o separador dos itens quando for aplicado o agregador do tipo `concat`, quando não informado o valor padrão é ```", "```.

#### GroupingInfo

Representa um nível de agrupamento a ser aplicado aos dados.

```DART linenums="1"
class GroupingInfo extends SortingInfo {
  
  String? groupInterval; // (1)

  num? numberInterval; // (2)
}
```

1. Um valor que agrupa dados em intervalos de um determinado comprimento ou período de data/hora.
    - Para quando o campo de dados do tipo de data pode ser `year`, `quarter`, `month`, `day`, `dayOfWeek`, `weekOfYear`, `hour`, `minute`, `second`.
    - Para quando o campo de dados do tipo de número o valor tem de ser `numberInterval`.
2. Define o número de intervalo que será agrupado, utilizado quando `groupInterval` for igual `numberInterval`.

!!! info "GroupingInfo herda de [SortingInfo](#sortinginfo) tendo todas as opções dela."

## Exemplos

??? example "Exemplos Baseados em Tabelas"
    Tabela com dados de exemplo:

    | Talhao      | Area | DataPlantio  |
    | ----------- | ---- | ------------ |
    | Talhão 1    | 20   | 2021-05-15   |
    | Talhão 2    | 30   | 2021-05-03   |
    | Talhão 3    | 11   | 2021-04-03   |

    === "LoadOptions com Ordenação"
        ```DART linenums="1"
        final loadOptions = LoadOptions(
          sort: SortingInfo(
            selector: 'Area',
            desc: true,
          ),
        );
        ```

    === "Resultado Ordenação"

        | Talhao      | Area :material-sort-numeric-descending: | DataPlantio |
        | ----------- | ---- | ------------ |
        | Talhão 2    | 30   | 2021-05-03   |
        | Talhão 1    | 20   | 2021-05-15   |
        | Talhão 3    | 11   | 2021-04-03   |

    <br>

    === "LoadOptions Filtro"
        ```DART linenums="1"
        final loadOptions = LoadOptions(
          sort: SortingInfo(
            selector: 'DataPlantio',
          ),
          filter: ['Area', '>', 15].
        );
        ```

    === "Resultado Filtro"

        | Talhao      | Area :material-filter: | DataPlantio :material-sort-calendar-ascending: |
        | ----------- | ---- | ------------ |
        | Talhão 2    | 30   | 2021-05-03   |
        | Talhão 1    | 20   | 2021-05-15   |
