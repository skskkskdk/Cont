// كود محدث لتطبيق "Cont" كوسيط تجاري يحتوي على نظام تسجيل دخول ومحادثة وفريق دعم وتحويل الأموال

import 'package:flutter/material.dart';

void main() => runApp(ContApp());

class ContApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Cont - وسيط الحسابات',
      theme: ThemeData(primarySwatch: Colors.indigo),
      home: WelcomeScreen(),
    );
  }
}

class WelcomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Padding(
          padding: const EdgeInsets.all(32.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Text(
                'مرحباً بك في Cont',
                style: TextStyle(fontSize: 28, fontWeight: FontWeight.bold),
              ),
              SizedBox(height: 40),
              ElevatedButton(
                onPressed: () {
                  Navigator.push(
                      context, MaterialPageRoute(builder: (_) => LoginScreen()));
                },
                child: Text('تسجيل الدخول'),
              ),
              TextButton(
                onPressed: () {
                  Navigator.push(
                      context, MaterialPageRoute(builder: (_) => RegisterScreen()));
                },
                child: Text('إنشاء حساب جديد'),
              )
            ],
          ),
        ),
      ),
    );
  }
}

class LoginScreen extends StatelessWidget {
  final TextEditingController emailController = TextEditingController();
  final TextEditingController passwordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('تسجيل الدخول')),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            TextField(
              controller: emailController,
              decoration: InputDecoration(labelText: 'البريد الإلكتروني / الهاتف'),
            ),
            TextField(
              controller: passwordController,
              obscureText: true,
              decoration: InputDecoration(labelText: 'كلمة المرور'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                // التحقق من الدخول
              },
              child: Text('دخول'),
            ),
          ],
        ),
      ),
    );
  }
}

class RegisterScreen extends StatelessWidget {
  final TextEditingController emailController = TextEditingController();
  final TextEditingController phoneController = TextEditingController();
  final TextEditingController passwordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('تسجيل حساب جديد')),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: SingleChildScrollView(
          child: Column(
            children: [
              TextField(
                controller: emailController,
                decoration: InputDecoration(labelText: 'البريد الإلكتروني'),
              ),
              TextField(
                controller: phoneController,
                decoration: InputDecoration(labelText: 'رقم الهاتف'),
              ),
              TextField(
                controller: passwordController,
                obscureText: true,
                decoration: InputDecoration(labelText: 'كلمة المرور'),
              ),
              SizedBox(height: 20),
              ElevatedButton(
                onPressed: () {
                  // إرسال رمز تحقق للبريد والهاتف
                },
                child: Text('متابعة'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
