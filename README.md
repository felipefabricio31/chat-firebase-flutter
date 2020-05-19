# Agenda de Contatos

<img src="" width="100%" heigth="auto">

App desenvolvido em Flutter com a opção de CRUD que salva as informações no Firebase e retorna em tempo real.
<p>Este app apresenta o conceito de Chat Online, </p>

## Introdução

Alguns recursos para você começar se este for seu primeiro projeto Flutter:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

Para obter ajuda sobre como iniciar o Flutter, consulte nosso
[online documentation](https://flutter.dev/docs), que oferece tutoriais,
amostras, orientações sobre desenvolvimento móvel e uma referência completa da API.

## Publicar app Flutter

[Tutorial](https://flutter.dev/docs/deployment/android)

## Alterar Ícone do App

[Tutorial 1](https://www.youtube.com/watch?v=e18HtjjoqFM)

## Instruções para o Firebase

<h4>Adiciona uma nova coleção no Firebase.</h4>
    <pre>
        Firestore.instance
        .collection("mensagens")
        .document("tHZFLRIWR2jv3gaZ1hls")
        .collection("arquivos")
        .document()
        .setData({"texto": "Felipe S", "from": "Felipe2", "read": false});
    </pre>

<h4>Retorna a lista de documentos, mas não é em tempo real.</h4>
    <pre>
        QuerySnapshot snapshot = await Firestore.instance.collection("mensagens").getDocuments();
        snapshot.documents.forEach((d) {
            print(d.data);
            print(d.documentID);
        });
    </pre>

<h4>Retorna apenas um documento.</h4>
    <pre>
        DocumentSnapshot snapshot = await Firestore.instance
        .collection("mensagens")
        .document("tHZFLRIWR2jv3gaZ1hls")
        .get();
        print(snapshot.data);
    </pre>

<h4>Retorna documentos e atualiza a lista em tempo real.</h4>
    <pre>
        Firestore.instance.collection("mensagens").snapshots().listen((dado) {
            dado.documents.forEach((d) {
                print(d.data);
            });
        });
    </pre>

<h4>Retorna o único documento em tempo real.</h4>
    <pre>
        Firestore.instance
        .collection("mensagens")
        .document("tHZFLRIWR2jv3gaZ1hls")
        .snapshots()
        .listen((dado) {
            print(dado.data);
        });
    </pre>
