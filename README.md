# Visualizador de modelos 3D (model_3d_flutter_sample)

Exemplo mínimo em **Flutter** que exibe um **modelo 3D interativo** (formato **glTF/GLB**) dentro do app, com rotação automática, controle de câmera por toque e **realidade aumentada (AR)** nos dispositivos compatíveis.

## O que o exemplo faz

A tela `MyApp3D` mostra um astronauta 3D carregado de uma URL pública. O usuário pode:

- girar, aproximar e afastar o modelo com os dedos (`cameraControls`);
- deixar o modelo girando sozinho (`autoRotate`);
- abrir o modelo em **AR**, projetando-o no ambiente real pela câmera (`ar`).

## Conceitos técnicos

**glTF / GLB.** Formato aberto para cenas 3D, o "JPEG do 3D": o `.glb` empacota geometria, materiais e texturas em um único arquivo binário.

**`<model-viewer>` dentro de uma WebView.** O pacote `model_viewer` embute o *web component* [`<model-viewer>`](https://modelviewer.dev/) do Google; o Flutter hospeda a página em uma WebView e faz a ponte com o app. Por isso o 3D roda sem código nativo de renderização.

**Origem do modelo.** O atributo `src` aceita uma URL remota (como no exemplo) ou um arquivo empacotado como *asset* do app.

**AR.** Com `ar: true`, o componente oferece a visualização em realidade aumentada usando os recursos do sistema (Scene Viewer no Android e Quick Look no iOS).

## Stack

Flutter · Dart · `model_viewer`

## Como executar

```bash
flutter pub get
flutter run
```

Requer conexão com a internet para baixar o modelo de exemplo. Para usar um modelo próprio, troque o `src` em `lib/main.dart` por outro `.glb`.

> O projeto usa um SDK antigo do Dart (`>=2.7.0 <3.0.0`); use uma versão compatível do Flutter (por exemplo via FVM).
