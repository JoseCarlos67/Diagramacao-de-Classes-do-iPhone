# 📱 Modelagem e Diagramação – Componente iPhone

Este projeto apresenta a **modelagem UML** do componente **iPhone**, inspirado na apresentação de 2007 em que Steve Jobs descreveu o dispositivo como **três produtos em um**:  
um reprodutor musical, um telefone e um navegador de Internet.  
Aqui, ampliamos o modelo para incluir também uma **lista de contatos**.

![iphone](UML-iPhone.png)

---

## 🎯 **Objetivo**

Demonstrar o uso de **interfaces**, **abstração** e **composição** em um modelo orientado a objetos.  
O diagrama apresenta o **iPhone** como uma classe que implementa três funcionalidades principais e mantém uma lista de contatos.

---

## 🧩 **Principais Elementos do Modelo**

### Interfaces
- 🎵 **ReprodutorMusical** — métodos: `tocar()`, `pausar()`, `selecionarMusica(String)`  
- ☎️ **AparelhoTelefonico** — métodos: `ligar(String)`, `atender()`, `iniciarCorreioVoz()`  
- 🌐 **NavegadorInternet** — métodos: `exibirPagina(String)`, `adicionarNovaAba()`, `atualizarPagina()`

## 🧱 **Diagrama UML (PlantUML)**

```plantuml
@startuml
interface ReprodutorMusical {
    + tocar()
    + pausar()
    + selecionarMusica(String)
}

interface AparelhoTelefonico {
    + ligar(String)
    + atender()
    + iniciarCorreioVoz()
}

interface NavegadorInternet {
    + exibirPagina(String)
    + adicionarNovaAba()
    + atualizarPagina()
}

class Contato {
    - nome: String
    - numero: String
    - email: String
}

class iPhone {
    - bateria: double
    - armazenamentoDisponivel: double
    - wifiConectado: boolean
    - musicaAtual: String
    - urlAtual: String
    - contatos: List<Contato>
}

iPhone ..|> ReprodutorMusical
iPhone ..|> AparelhoTelefonico
iPhone ..|> NavegadorInternet
iPhone *-- "1..*" Contato
@enduml
```

Use um renderizador PlantUML, como:
- [PlantText](https://www.planttext.com/)  
- [PlantUML Editor Online](https://plantuml-editor.kkeisuke.app/)  
- Extensão **PlantUML** no VSCode  

---

## 🧠 **Conceitos de POO aplicados**

- **Abstração**: definição de contratos por interfaces.  
- **Encapsulamento**: controle de atributos e comportamento interno.  
- **Polimorfismo**: implementação de múltiplas interfaces por uma única classe.  
- **Composição**: o `iPhone` contém e gerencia seus próprios contatos.  

---

## 🧾 **Créditos**

Desenvolvido como parte de um exercício da plataforme **DIO**.  
Inspirado no vídeo de lançamento do iPhone (2007).
