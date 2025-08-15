# facul-projeto-iot

Desenvolvimento de Hardware para IoT.

```mermaid
graph TD
    A["Alimentação 5V / USB-C"] --> B{"Módulo Regulador 3.3V"}
    B --> C["ESP32-C3 Microcontrolador"]

    C -- I2C --> D["Sensor BME280 (Temp, Umid, Pressão)"]
    C -- GPIO (ADC) --> E["Sensor MQ-135 (Gases Poluentes)"]
    C -- Serial (UART) --> F["Sensor PMS5003 (Material Particulado)"]
    C -- I2C --> G["Display OLED 0.96"]
    C -- GPIO --> H["Botão de Ação"]

    C -- Wi-Fi --> I["Internet"]
    I -- MQTT/HTTPS --> J["Plataforma IoT (AWS IoT Core, Google Cloud IoT Core)"]
    J -- Armazenamento/Análise --> K["Banco de Dados / Serviço de Análise"]
    K -- Visualização/Alertas --> L["Dashboard Web / Aplicativo Móvel"]

