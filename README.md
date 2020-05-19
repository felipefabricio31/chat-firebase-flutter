# chat_firebase

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## Instruções para o Firebase

Firestore.instance
.collection("mensagens")
.document("tHZFLRIWR2jv3gaZ1hls")
.collection("arquivos")
.document()
.setData({"texto": "Felipe S", "from": "Felipe2", "read": false});

//Unica busca
QuerySnapshot snapshot =
await Firestore.instance.collection("mensagens").getDocuments();
snapshot.documents.forEach((d) {
print(d.data);
print(d.documentID);
});

  <h4>Unico doc</h4>
    <pre>
        DocumentSnapshot snapshot = await Firestore.instance
        .collection("mensagens")
        .document("tHZFLRIWR2jv3gaZ1hls")
        .get();
        print(snapshot.data);   
    </pre>

<h4>Atualiza em tempo real</h4>
    <pre>
        Firestore.instance.collection("mensagens").snapshots().listen((dado) {
            dado.documents.forEach((d) {
                print(d.data);
            });
        });
    </pre>

<h4>Unico documento em tempo real</h4>

    <pre>
        Firestore.instance
        .collection("mensagens")
        .document("tHZFLRIWR2jv3gaZ1hls")
        .snapshots()
        .listen((dado) {
            print(dado.data);
        });
    </pre>
