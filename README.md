# get_image
import 'dart:io';
import 'package:flutter/material.dart';
import 'package:image_picker/image_picker.dart';

class FilterFireStore extends StatefulWidget {
  const FilterFireStore({super.key});

  @override
  State<FilterFireStore> createState() => _FilterFireStore();
}

class _FilterFireStore extends State<FilterFireStore> {
  File? file;
  getImage() async {
    final ImagePicker picker = ImagePicker();

    final XFile? photo = await picker.pickImage(source: ImageSource.camera);
    file = File(photo!.path);
    setState(() {});
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: Text('Filter'),
        ),
        body: Container(
            padding: const EdgeInsets.all(10),
            child: Column(
              children: [
                MaterialButton(
                  onPressed: () {
                    getImage();
                  },
                  child: Text("Get Image"),
                ),
                if (file != null) Image.file(file!)
              ],
            )));
  }
}
// Pick an image.
   // final XFile? image = await picker.pickImage(source: ImageSource.gallery);
// Capture a photo.


/* DocumentReference documentReference = FirebaseFirestore
                      .instance
                      .collection('users')
                      .doc(data[i].id);

                  documentReference.update({"money": data[i]['money'] + 100});
                  // Navigator.of(context)
                  // .pushAndRemoveUntil("FilterFireStore", (route) => false);

                  /*FirebaseFirestore.instance
                      .runTransaction((transaction) async {
                    DocumentSnapshot snapshot =
                        await transaction.get(documentReference);
                    if (snapshot.exists) {
                      //var data = snapshotData as Map<String, dynamic>;
                      //int money = data['money'] + 100;

                      var data = snapshotData as Map<String, dynamic>;
                      if (snapshot is Map<String, dynamic>) {
                        int money = data['money'] + 100;
                        transaction.update(documentReference, {"money": money});
                      }
                    }
                  });*/*/

 /*floatingActionButton: FloatingActionButton(
        onPressed: () {
          CollectionReference users =
              FirebaseFirestore.instance.collection('users');
          DocumentReference doc1 =
              FirebaseFirestore.instance.collection('users').doc("1");
          DocumentReference doc2 =
              FirebaseFirestore.instance.collection('users').doc("2");

          WriteBatch batch = FirebaseFirestore.instance.batch();
          batch.set(doc1, {"username": "ahmed", "money": 145, "age": 30});
          batch.set(doc2, {"username": "wezaa", "money": 2000, "age": 20});
          batch.commit();
        },*/

        /*
        const Icon(Icons.add),
      ),
      body: Container(
        child: ListView.builder(
            itemCount: data.length,
            itemBuilder: (context, i) {
              Card(
                  child: ListTile(
                trailing: Text(
                  "${data[i]['money']}\$",
                  style: TextStyle(color: Colors.red),
                ),
                subtitle: Text("age: ${data[i]['age']}"),
                title: Text(
                  data[i]['username'],
                  style: TextStyle(fontSize: 30),
                ),
              ));
            }),
      ),
         */ 

  /*
   child: StreamBuilder(
              stream: userstream,
              builder: (context, AsyncSnapshot<QuerySnapshot> snapshot) {
                if (snapshot.hasError) {
                  return Text("Error");
                }
                if (snapshot.connectionState == ConnectionState.waiting) {
                  return Text("Loading...");
                }
                return ListView.builder(
                    itemCount: snapshot.data!.docs.length,
                    itemBuilder: (context, i) {
                      return Card(
                          child: ListTile(
                              subtitle:
                                  Text("${snapshot.data!.docs[i]['age']}"),
                              title: Text(
                                  "${snapshot.data!.docs[i]['username']}")));
                    });
              }),*/

              
    /*final Stream<QuerySnapshot> userstream =
      FirebaseFirestore.instance.collection('users').snapshots();

  //List<QueryDocumentSnapshot> data = [];

  @override
  void initState() {
    super.initState();
  }*/                                
