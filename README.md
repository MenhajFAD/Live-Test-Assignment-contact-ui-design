# Live-Test-Assignment-contact-ui-designimport 'package:flutter/material.dart';
class LiveTest extends StatelessWidget {
  const LiveTest({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Contact List'),
        centerTitle: true,
        backgroundColor: Colors.blueGrey,
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            // Name Input Field
            TextFormField(
              decoration: const InputDecoration(
                hintText: 'Name',
                border: OutlineInputBorder(),
              ),
            ),
            const SizedBox(height: 10),
            // Number Input Field
            TextFormField(
              decoration: const InputDecoration(
                hintText: 'Number',
                border: OutlineInputBorder(),
              ),
              keyboardType: TextInputType.phone,
            ),
            const SizedBox(height: 15),
            // Add Button
            SizedBox(
              width: double.infinity,
              child: ElevatedButton(
                style: ElevatedButton.styleFrom(
                  backgroundColor: Colors.blueGrey,
                  shape: RoundedRectangleBorder(
                    borderRadius: BorderRadius.circular(5),
                  ),
                ),
                onPressed: () {}, // Functionality lagbe na bola hoyeche
                child: const Text('Add', style: TextStyle(color: Colors.white)),
              ),
            ),
            const SizedBox(height: 20),
            // Contact List Item (Sample Data)
            Expanded(
              child: ListView(
                children: const [
                  ContactItem(name: 'Jawad', number: '01877-777777'),
                  ContactItem(name: 'Ferdous', number: '01673-777777'),
                  ContactItem(name: 'Hasan', number: '01745-777777'),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}

// ListTile Widget for the items
class ContactItem extends StatelessWidget {
  final String name;
  final String number;

  const ContactItem({super.key, required this.name, required this.number});

  @override
  Widget build(BuildContext context) {
    return Card(
      color: Colors.grey[200],
      child: ListTile(
        leading: const Icon(Icons.person, color: Colors.brown),
        title: Text(name, style: const TextStyle(color: Colors.red, fontWeight: FontWeight.bold)),
        subtitle: Text(number),
        trailing: const Icon(Icons.phone, color: Colors.blue),
      ),
    );
  }
}

