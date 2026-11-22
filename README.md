import 'package:flutter/material.dart';

void main() {
  runApp(const MeuPlayerIPTV());
}

class MeuPlayerIPTV extends StatelessWidget {
  const MeuPlayerIPTV({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData.dark(),
      home: const TelaLogin(),
      debugShowCheckedModeBanner: false,
    );
  }
}

class TelaLogin extends StatefulWidget {
  const TelaLogin({super.key});

  @override
  State<TelaLogin> createState() => _TelaLoginState();
}

class _TelaLoginState extends State<TelaLogin> {
  final TextEditingController usuario = TextEditingController();
  final TextEditingController senha = TextEditingController();
  final TextEditingController dns = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color(0xFF0F1A30),
      body: Padding(
        padding: const EdgeInsets.all(24.0),
        child: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              const Icon(Icons.play_circle_fill, color: Colors.blue, size: 80),
              const SizedBox(height: 30),
              TextField(
                controller: usuario,
                decoration: const InputDecoration(
                  labelText: "Usuário",
                  filled: true,
                  fillColor: Colors.white10,
                  border: OutlineInputBorder(),
                ),
              ),
              const SizedBox(height: 12),
              TextField(
                controller: senha,
                obscureText: true,
                decoration: const InputDecoration(
                  labelText: "Senha",
                  filled: true,
                  fillColor: Colors.white10,
                  border: OutlineInputBorder(),
                ),
              ),
              const SizedBox(height: 12),
              TextField(
                controller: dns,
                decoration: const InputDecoration(
                  labelText: "DNS / URL",
                  filled: true,
                  fillColor: Colors.white10,
                  border: OutlineInputBorder(),
                ),
              ),
              const SizedBox(height: 30),
              SizedBox(
                width: double.infinity,
                child: ElevatedButton(
                  style: ElevatedButton.styleFrom(
                    backgroundColor: Colors.blue,
                    padding: const EdgeInsets.all(16),
                  ),
                  onPressed: () {
                    String user = usuario.text.trim();
                    String pass = senha.text.trim();
                    String servidor = dns.text.trim();

                    if(user.isNotEmpty && pass.isNotEmpty && servidor.isNotEmpty){
                      ScaffoldMessenger.of(context).showSnackBar(
                        const SnackBar(content: Text("Conectando ao servidor..."))
                      );
                    }
                  },
                  child: const Text("ENTRAR", style: TextStyle(fontSize: 18)),
                ),
              )
            ],
          ),
        ),
      ),
    );
  }
}# teste
