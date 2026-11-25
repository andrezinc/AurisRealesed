<p align="center">
  <img src="Absorve-Visual/Assets.xcassets/AppIcon.appiconset/LOGO%20icon_light.jpg" alt="Ícone do Auris" width="160">
</p>

<h1 align="center">Auris</h1>

<p align="center"><strong>Mais autonomia para conhecer o que está na embalagem.</strong></p>

<p align="center">
  Fotografe uma embalagem de absorvente e receba uma descrição das suas características.
</p>

<p align="center">
  <a href="#sobre">Sobre</a> ·
  <a href="#como-funciona">Como funciona</a> ·
  <a href="#acessibilidade">Acessibilidade</a> ·
  <a href="#identidade-visual">Identidade visual</a> ·
  <a href="#tecnologias">Tecnologias</a> ·
  <a href="#executando-o-projeto">Executando o projeto</a> ·
  <a href="#equipe">Equipe</a>
</p>

## Sobre

**Auris** é um aplicativo para iPhone que usa a câmera e inteligência artificial para descrever embalagens de absorventes. A proposta é facilitar o acesso às informações do produto e apoiar a autonomia de pessoas cegas ou com baixa visão na hora de escolher.

A partir de uma foto, o app organiza informações como nome, tipo de uso, fluxo, cobertura, presença de abas, quantidade e fragrância. Uma descrição geral complementa os dados com detalhes visuais da embalagem.

| Plataforma | Foco | Interface |
| --- | --- | --- |
| iPhone · iOS | Acessibilidade e identificação de produtos | SwiftUI |

## Como funciona

1. **Conheça o Auris:** uma apresentação inicial explica o uso do aplicativo.
2. **Tire uma foto:** enquadre a embalagem e capture a imagem, com opção de iluminação pela lanterna.
3. **Receba a descrição:** a imagem é enviada à API da OpenAI, que retorna as informações organizadas do produto.
4. **Explore os detalhes:** consulte os dados principais e a descrição geral da embalagem, com apoio do VoiceOver.
5. **Fotografe novamente:** retorne à câmera para consultar outro produto.

O reconhecimento depende de conexão com a internet e de uma chave de API configurada. Quando a análise não identifica um absorvente, o fluxo prevê o retorno de informações como “não encontrado”.

## Acessibilidade

A interface inclui recursos para navegação com **VoiceOver**:

- Rótulos nos controles de captura e iluminação, com indicação do estado da lanterna.
- Agrupamento de informações para uma leitura contínua dos componentes.
- Foco de acessibilidade no nome do produto ao apresentar o resultado.
- Descrições das ilustrações informativas e ocultação de ícones decorativos na leitura.

## Identidade visual

O Auris combina tons de verde, formas arredondadas e ilustrações que relacionam compras, produtos e comunicação. As cores possuem variações para as aparências clara e escura.

<p align="center">
  <img src="Absorve-Visual/Assets.xcassets/onboardingImage.imageset/ilustra_claro.svg" alt="Ilustração de apresentação do Auris: cesta de compras, balão com ondas sonoras e ícones de absorventes" width="420">
</p>

| Cor | Aparência clara | Aparência escura |
| --- | --- | --- |
| Verde primário | `#A7FF9D` | `#03625A` |
| Verde secundário | `#03625A` | `#A7FF9D` |

## Tecnologias

| Tecnologia | Papel no projeto |
| --- | --- |
| Swift | Lógica do aplicativo e integração entre as camadas |
| SwiftUI | Telas, navegação e componentes de interface |
| AVFoundation | Captura de fotos, prévia da câmera e controle da lanterna |
| OpenAI · GPT-4o mini | Análise da imagem e geração da descrição estruturada |
| OpenAI para Swift, da MacPaw | Comunicação com a API da OpenAI |
| Swift Package Manager | Gerenciamento das dependências |

O código está organizado em **Views**, **ViewModels**, **Models**, **Repository**, **Services** e **Camera**, separando apresentação, estado, dados, integração com a API e captura de imagens.

## Executando o projeto

### Requisitos

- macOS com Xcode e SDK compatível com o projeto.
- iPhone com **iOS 17.6 ou superior**, versão mínima configurada no target do aplicativo.
- Conexão com a internet e uma chave da API da OpenAI com acesso ao modelo utilizado.

### Configuração

1. Clone o repositório:

   ```bash
   git clone https://github.com/andrezinc/AurisRealesed.git
   cd AurisRealesed
   ```

2. Abra `Absorve-Visual.xcodeproj` no Xcode e aguarde a resolução das dependências pelo Swift Package Manager.
3. Crie um arquivo local `Segredinho.swift` dentro de `Absorve-Visual`, incluído no target do app, com a definição esperada pelo serviço:

   ```swift
   enum Segredinho {
       static let OPENAI_KEY = "SUA_CHAVE_DA_API"
   }
   ```

   Esse arquivo não acompanha o repositório. Mantenha a chave apenas no ambiente local e adicione `Segredinho.swift` ao seu `.git/info/exclude` para evitar seu envio em commits.

4. Selecione o scheme **Absorve-Visual** e configure sua equipe em **Signing & Capabilities**.
5. Escolha o iPhone conectado como destino e execute com **⌘R**. Autorize o acesso à câmera quando solicitado.

Use um dispositivo físico para experimentar o fluxo de captura de fotos.

O projeto e a pasta de código mantêm o nome original **Absorve-Visual**; o aplicativo é apresentado como **Auris**.

## Equipe

O Auris foi construído com a participação de:

| Integrante | GitHub |
| --- | --- |
| André Castilhano | [@andrezinc](https://github.com/andrezinc) |
| Beatriz Perotto Muniz | [@beatrizperottomuniz](https://github.com/beatrizperottomuniz) |
| Alana | [@alanaqroz](https://github.com/alanaqroz) |
| Muchinski25 | [@Muchinski25](https://github.com/Muchinski25) |
| Camile | — |

## Licença

Este projeto está sob a licença **Creative Commons Atribuição-NãoComercial 4.0 Internacional (CC BY-NC 4.0)**. Consulte o arquivo [LICENSE](LICENSE).

---

Estrutura de apresentação inspirada no README do [Meowsic](https://github.com/andrezinc/Meowsic), de [andrezinc](https://github.com/andrezinc).
