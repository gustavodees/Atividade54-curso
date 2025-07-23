# Conversão de Instant para Data e Hora em Diferentes Timezones e Extração de Componentes em Java

Este projeto consiste em um programa Java simples que demonstra como converter um objeto `Instant` (que representa um ponto na linha do tempo em UTC) para objetos `LocalDate` (data) e `LocalDateTime` (data e hora) em diferentes timezones. Além disso, o código mostra como extrair componentes específicos de um objeto `LocalDateTime`, como dia, mês, ano, hora, minuto e segundo.

**Autor:** gustavodees

## Arquivos Incluídos

* `principal/Main.java`: Contém a classe principal com o método `main`, onde as operações de conversão e extração de componentes de data e hora são demonstradas.

## Como Usar

1.  **Salve o arquivo:** Salve o código fornecido em um arquivo chamado `Main.java` dentro de uma pasta chamada `principal`.
2.  **Compile o código:** Abra um terminal ou prompt de comando, navegue até o diretório raiz do seu projeto e compile o arquivo Java utilizando o compilador Java:

    ```bash
    javac principal/Main.java
    ```

3.  **Execute o programa:** Após a compilação ser concluída com sucesso, execute a classe `Main` com o comando:

    ```bash
    java principal.Main
    ```

4.  **Resultado:** O programa exibirá no console as seguintes informações:
    * A representação de um `Instant` convertido para `LocalDate` utilizando o timezone padrão do sistema.
    * A representação do mesmo `Instant` convertido para `LocalDate` utilizando o timezone de Portugal.
    * A representação do mesmo `Instant` convertido para `LocalDateTime` utilizando o timezone padrão do sistema.
    * A representação do mesmo `Instant` convertido para `LocalDateTime` utilizando o timezone de Portugal.
    * Os componentes individuais (dia, mês, ano, hora, minuto e segundo) de um objeto `LocalDateTime` específico.

## Explicação do Código

### `principal/Main.java`

Este arquivo contém a classe `Main`, que é o ponto de entrada do programa e demonstra a conversão de `Instant` e a extração de componentes de data e hora.

* **Método `main`:**
    1.  **Criação de objetos de data e hora:** São criados objetos de diferentes classes do `java.time`:
        * `LocalDate d01 = LocalDate.now()`: Obtém a data atual.
        * `LocalDateTime d02 = LocalDateTime.parse("2022-07-20T01:30:26")`: Cria um objeto `LocalDateTime` a partir de uma string no formato ISO 8601.
        * `Instant d03 = Instant.parse("2022-07-20T01:30:26Z")`: Cria um objeto `Instant` a partir de uma string no formato ISO 8601 UTC.
    2.  **Conversão de `Instant` para `LocalDate` e `LocalDateTime` com Timezones:**
        * `LocalDate r1 = LocalDate.ofInstant(d03, ZoneId.systemDefault())`: Converte o `Instant` `d03` para um `LocalDate` utilizando o timezone padrão do sistema (`ZoneId.systemDefault()`).
        * `LocalDate r2 = LocalDate.ofInstant(d03, ZoneId.of("Portugal"))`: Converte o `Instant` `d03` para um `LocalDate` utilizando o timezone de Portugal (`ZoneId.of("Portugal")`). É importante notar que os nomes dos timezones seguem o padrão "Região/Cidade".
        * `LocalDateTime r3 = LocalDateTime.ofInstant(d03, ZoneId.systemDefault())`: Converte o `Instant` `d03` para um `LocalDateTime` utilizando o timezone padrão do sistema.
        * `LocalDateTime r4 = LocalDateTime.ofInstant(d03, ZoneId.of("Portugal"))`: Converte o `Instant` `d03` para um `LocalDateTime` utilizando o timezone de Portugal.
    3.  **Impressão dos resultados das conversões:** Os objetos `LocalDate` e `LocalDateTime` resultantes das conversões são impressos no console.
    4.  **Extração de componentes de `LocalDateTime`:**
        * `d02.getDayOfMonth()`: Obtém o dia do mês do objeto `d02`.
        * `d02.getMonthValue()`: Obtém o valor numérico do mês do objeto `d02`.
        * `d02.getYear()`: Obtém o ano do objeto `d02`.
        * `d02.getHour()`: Obtém a hora do objeto `d02`.
        * `d02.getMinute()`: Obtém o minuto do objeto `d02`.
        * `d02.getSecond()`: Obtém o segundo do objeto `d02`.
    5.  **Impressão dos componentes de `LocalDateTime`:** Os componentes extraídos do objeto `d02` são impressos no console com descrições.
