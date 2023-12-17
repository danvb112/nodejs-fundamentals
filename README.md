# Nodejs Fundamentals

## Streams

Streams são uma forma se trabalhar com dados antes deles estarem completos. Existem 3 tipos mais comuns de streams no node:

### 1 - Readable Streams

Readable Streams são uma parte do módulo de Streams, que fornece uma maneira de ler dados de uma fonte de maneira eficiente, especialmente quando se lida com grandes conjuntos de dados. As Readable Streams permitem que você consuma dados de uma fonte, como um arquivo ou uma solicitação de HTTP, de maneira assíncrona e eficiente, à medida que os dados estão disponíveis.

Principais características das Readable Streams:

1. Assincronia: A leitura de dados é não bloqueante, permitindo que o programa continue executando outras tarefas enquanto aguarda a disponibilidade de dados.

2. Eventos: As Readable Streams emitem eventos, como 'data' quando novos dados estão disponíveis para leitura e 'end' quando não há mais dados para ler.

3. Modo de Fluxo (Flow Mode): As Readable Streams operam em um modo de fluxo, o que significa que os dados são fornecidos automaticamente à medida que estão disponíveis, em vez de serem lidos manualmente.

4. Buffering: Os dados lidos são armazenados em um buffer, e você pode controlar o tamanho desse buffer para otimizar o desempenho.

### 2 - Writable Streams

Writable Streams são outra parte do módulo de Streams que oferece uma maneira eficiente de escrever dados para um destino, como um arquivo ou uma resposta HTTP. Assim como as Readable Streams, as Writable Streams são projetadas para lidar com grandes volumes de dados de maneira assíncrona e eficiente.

Principais características das Writable Streams:

1. Assincronia: A escrita de dados é não bloqueante, permitindo que o programa continue executando outras tarefas enquanto os dados estão sendo gravados.

2. Eventos: As Writable Streams emitem eventos, como 'drain' quando o buffer está vazio e pronto para aceitar mais dados, 'finish' quando todos os dados foram escritos e 'error' em caso de erro durante a escrita.

3. Buffering: Os dados são escritos em um buffer antes de serem efetivamente gravados no destino. O buffer ajuda a otimizar a operação de gravação.

4. Modo de Fluxo (Flow Mode): Assim como nas Readable Streams, as Writable Streams operam em um modo de fluxo, permitindo que os dados sejam escritos automaticamente à medida que são recebidos.

### 3 - Transform Streams

Transform Streams são uma categoria especial de streams que combinam características de Readable Streams e Writable Streams. Eles são utilizados para processar e transformar dados à medida que são lidos de uma fonte antes de serem escritos em um destino. Transform Streams são úteis quando você precisa modificar ou manipular dados enquanto estão em trânsito entre a origem e o destino.

Principais características das Transform Streams:

1. Duplex: Transform Streams são duplex, o que significa que eles podem ser usados tanto para leitura quanto para escrita. Eles têm tanto uma parte de leitura (Readable) quanto uma parte de escrita (Writable).

2. Assincronia: Assim como Readable e Writable Streams, a transformação de dados é realizada de forma não bloqueante, permitindo que o programa continue executando outras tarefas.

3. Eventos: Transform Streams emitem eventos similares aos de Readable e Writable Streams, como 'data' para dados disponíveis para leitura, 'end' quando não há mais dados para ler, 'finish' quando todos os dados foram escritos e 'error' em caso de erro durante a transformação.

4. Pipeline: Transform Streams são frequentemente usados em conjunto com o método pipeline para facilitar a criação de tubulações de processamento de dados.

## Buffers

O Buffer é uma representação de um espaço na memória do computador, usado especificamente para transitar dados de uma maneira muito rápida. Os dados armazenados no Buffer são alocados ali para serem tratados posteriormente e enviados para outro lugar, sendo removidos em seguida. Dessa forma, o Buffer oferece maneiras eficientes de salvar e ler dados na memória.

O Node utiliza o modelo de Buffer na leitura e escrita de Streams, pois é mais eficiente ler parcialmente uma informação binária do que uma string, por exemplo. A eficiência do Buffer é particularmente útil em situações em que o desempenho é crucial, como operações de entrada/saída de baixo nível, processamento de arquivos binários e comunicação de rede.

O Buffer foi incorporado ao Node justamente devido à limitação do JavaScript em lidar de forma eficiente com dados binários. Ele proporciona uma solução eficaz para a manipulação direta e rápida de dados binários, preenchendo uma lacuna na capacidade padrão da linguagem JavaScript. 
