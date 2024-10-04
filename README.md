# Projeto de Monitoramento com ESP32 e MQTT

Este projeto utiliza um ESP32 para monitorar a temperatura, umidade e luminosidade, enviando os dados para um broker MQTT. O código também permite o controle de um LED onboard via comandos MQTT.

## Integrantes:
- Milena Codinhoto
- Evellyn Valencia
- Carolina Ferraz
  
## Componentes Utilizados

- ESP32
- Sensor DHT11
- Potenciômetro (para medir luminosidade)
- LED onboard

## Bibliotecas Necessárias

- WiFi
- PubSubClient
- DHT

## Configurações

### Wi-Fi

- **SSID**: `FIAP-IBM`
- **Senha**: `Challenge@24!`

### Broker MQTT

- **IP**: `18.208.160.16`
- **Porta**: `1883`
- **ID MQTT**: `fiware_003`

### Tópicos MQTT

- **Subscribe**: `/TEF/device003/cmd`
- **Publish**:
  - `/TEF/device003/attrs`
  - `/TEF/device003/attrs/p`
  - `/TEF/device003/attrs/dht`

## Pinos Utilizados

- **DHT11**: Pino `15`
- **LED onboard**: Pino `2`
- **Potenciômetro**: Pino `34`

## Funcionalidades

1. **Conexão Wi-Fi**: Conecta o ESP32 à rede Wi-Fi configurada.
2. **Conexão MQTT**: Conecta ao broker MQTT e se inscreve no tópico de comandos.
3. **Leitura de Sensores**:
   - **DHT11**: Lê temperatura e umidade.
   - **Potenciômetro**: Lê o valor de luminosidade.
4. **Publicação MQTT**: Envia os dados lidos para os tópicos configurados.
5. **Controle do LED**: Liga ou desliga o LED onboard baseado nos comandos recebidos via MQTT.

## Como Usar

1. **Configurar o Wi-Fi e Broker MQTT**: Edite as variáveis `default_SSID`, `default_PASSWORD`, `default_BROKER_MQTT` e `default_BROKER_PORT` com suas configurações de rede e broker MQTT.
2. **Carregar o Código no ESP32**: Utilize a IDE Arduino para carregar o código no ESP32.
3. **Monitorar e Controlar**: Utilize um cliente MQTT para monitorar os dados publicados e enviar comandos para controlar o LED.

## Exemplo de Comandos MQTT

- **Ligar LED**: Publique `device003@on|` no tópico `/TEF/device003/cmd`.
- **Desligar LED**: Publique `device003@off|` no tópico `/TEF/device003/cmd`.

---

Espero que isso ajude! Se precisar de mais alguma coisa, é só avisar. 😊
