```dart
import 'package:flutter/material.dart';
import 'dart:ui';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData(
        useMaterial3: true,
        colorScheme: ColorScheme.fromSeed(
          seedColor: Colors.blue,
          brightness: Brightness.light,
        ),
      ),
      initialRoute: "/login",
      routes: {
        "/login": (context) => LoginPage(),
        "/main": (context) => MainPage(),
        "/faq": (context) => FAQPage(),
        "/register": (context) => RegisterPage(),
        "/calculator": (context) => CalculatorPage(),
      },
    );
  }
}

// Página de Login Mejorada
class LoginPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Stack(
        children: [
          // Fondo con gradiente
          Container(
            decoration: BoxDecoration(
              gradient: LinearGradient(
                begin: Alignment.topLeft,
                end: Alignment.bottomRight,
                colors: [
                  Color(0xFF4158D0),
                  Color(0xFFC850C0),
                  Color(0xFFFFCC70),
                ],
              ),
            ),
          ),
          
          // Formas decorativas
          Positioned(
            top: -100,
            left: -50,
            child: Container(
              width: 200,
              height: 200,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.3),
                borderRadius: BorderRadius.circular(100),
              ),
            ),
          ),
          
          Positioned(
            bottom: -80,
            right: -50,
            child: Container(
              width: 180,
              height: 180,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.2),
                borderRadius: BorderRadius.circular(90),
              ),
            ),
          ),
          
          // Contenido principal con blur
          Center(
            child: ClipRRect(
              borderRadius: BorderRadius.circular(20),
              child: BackdropFilter(
                filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                child: Container(
                  width: 320,
                  padding: EdgeInsets.all(30),
                  decoration: BoxDecoration(
                    color: Colors.white.withOpacity(0.2),
                    borderRadius: BorderRadius.circular(20),
                    border: Border.all(
                      color: Colors.white.withOpacity(0.2),
                      width: 1.5,
                    ),
                    boxShadow: [
                      BoxShadow(
                        color: Colors.black.withOpacity(0.1),
                        blurRadius: 20,
                        spreadRadius: 5,
                      ),
                    ],
                  ),
                  child: Column(
                    mainAxisSize: MainAxisSize.min,
                    children: [
                      Text(
                        "Iniciar Sesión",
                        style: TextStyle(
                          fontSize: 24,
                          fontWeight: FontWeight.bold,
                          color: Colors.white,
                        ),
                      ),
                      SizedBox(height: 30),
                      // Campo de usuario con estilo moderno
                      TextField(
                        style: TextStyle(color: Colors.white),
                        decoration: InputDecoration(
                          hintText: 'Usuario',
                          hintStyle: TextStyle(color: Colors.white70),
                          prefixIcon: Icon(Icons.person, color: Colors.white70),
                          enabledBorder: OutlineInputBorder(
                            borderRadius: BorderRadius.circular(10),
                            borderSide: BorderSide(color: Colors.white38),
                          ),
                          focusedBorder: OutlineInputBorder(
                            borderRadius: BorderRadius.circular(10),
                            borderSide: BorderSide(color: Colors.white),
                          ),
                          filled: true,
                          fillColor: Colors.white.withOpacity(0.1),
                        ),
                      ),
                      SizedBox(height: 20),
                      // Campo de contraseña con estilo moderno
                      TextField(
                        obscureText: true,
                        style: TextStyle(color: Colors.white),
                        decoration: InputDecoration(
                          hintText: 'Contraseña',
                          hintStyle: TextStyle(color: Colors.white70),
                          prefixIcon: Icon(Icons.lock, color: Colors.white70),
                          enabledBorder: OutlineInputBorder(
                            borderRadius: BorderRadius.circular(10),
                            borderSide: BorderSide(color: Colors.white38),
                          ),
                          focusedBorder: OutlineInputBorder(
                            borderRadius: BorderRadius.circular(10),
                            borderSide: BorderSide(color: Colors.white),
                          ),
                          filled: true,
                          fillColor: Colors.white.withOpacity(0.1),
                        ),
                      ),
                      SizedBox(height: 30),
                      // Botón de iniciar sesión con efecto de cristal
                      ElevatedButton(
                        style: ElevatedButton.styleFrom(
                          foregroundColor: Colors.white,
                          backgroundColor: Colors.white.withOpacity(0.3),
                          padding: EdgeInsets.symmetric(horizontal: 50, vertical: 15),
                          shape: RoundedRectangleBorder(
                            borderRadius: BorderRadius.circular(10),
                          ),
                        ),
                        child: Text(
                          "INGRESAR",
                          style: TextStyle(
                            fontSize: 16,
                            fontWeight: FontWeight.bold,
                          ),
                        ),
                        onPressed: () {
                          Navigator.pushReplacementNamed(context, "/main");
                        },
                      ),
                    ],
                  ),
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
}

// Página Principal Mejorada
class MainPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      extendBodyBehindAppBar: true,
      appBar: AppBar(
        backgroundColor: Colors.transparent,
        elevation: 0,
        title: Text(
          "Menú Principal",
          style: TextStyle(
            color: Colors.white,
            fontWeight: FontWeight.bold,
          ),
        ),
      ),
      body: Stack(
        children: [
          // Fondo con gradiente
          Container(
            decoration: BoxDecoration(
              gradient: LinearGradient(
                begin: Alignment.topRight,
                end: Alignment.bottomLeft,
                colors: [
                  Color(0xFF0A2463),
                  Color(0xFF3E92CC),
                  Color(0xFF2176AE),
                ],
              ),
            ),
          ),
          
          // Formas decorativas
          Positioned(
            top: 100,
            right: -20,
            child: Container(
              width: 150,
              height: 150,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.2),
                borderRadius: BorderRadius.circular(75),
              ),
            ),
          ),
          
          Positioned(
            bottom: 100,
            left: -50,
            child: Container(
              width: 200,
              height: 200,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.1),
                borderRadius: BorderRadius.circular(100),
              ),
            ),
          ),
          
          // Contenido principal
          Center(
            child: Padding(
              padding: EdgeInsets.symmetric(horizontal: 20),
              child: ClipRRect(
                borderRadius: BorderRadius.circular(25),
                child: BackdropFilter(
                  filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                  child: Container(
                    padding: EdgeInsets.all(30),
                    decoration: BoxDecoration(
                      color: Colors.white.withOpacity(0.15),
                      borderRadius: BorderRadius.circular(25),
                      border: Border.all(
                        color: Colors.white.withOpacity(0.2),
                        width: 1.5,
                      ),
                    ),
                    child: Column(
                      mainAxisSize: MainAxisSize.min,
                      children: [
                        // Título centrado
                        Text(
                          "Opciones",
                          style: TextStyle(
                            fontSize: 22,
                            fontWeight: FontWeight.bold,
                            color: Colors.white,
                          ),
                        ),
                        SizedBox(height: 30),
                        
                        // Botones con estilo moderno
                        _buildGlassButton(
                          context,
                          "Preguntas Frecuentes",
                          Icons.question_answer,
                          "/faq",
                        ),
                        SizedBox(height: 15),
                        
                        _buildGlassButton(
                          context,
                          "Registro",
                          Icons.app_registration,
                          "/register",
                        ),
                        SizedBox(height: 15),
                        
                        _buildGlassButton(
                          context,
                          "Calculadora",
                          Icons.calculate,
                          "/calculator",
                        ),
                        SizedBox(height: 40),
                        
                        // Botón de cerrar sesión
                        ElevatedButton.icon(
                          icon: Icon(Icons.exit_to_app, color: Colors.white),
                          label: Text(
                            "Cerrar Sesión", 
                            style: TextStyle(color: Colors.white),
                          ),
                          style: ElevatedButton.styleFrom(
                            backgroundColor: Colors.red.withOpacity(0.3),
                            padding: EdgeInsets.symmetric(horizontal: 30, vertical: 12),
                            shape: RoundedRectangleBorder(
                              borderRadius: BorderRadius.circular(10),
                            ),
                          ),
                          onPressed: () {
                            Navigator.pushReplacementNamed(context, "/login");
                          },
                        ),
                      ],
                    ),
                  ),
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
  
  // Método para crear botones de cristal
  Widget _buildGlassButton(BuildContext context, String text, IconData icon, String route) {
    return Container(
      width: double.infinity,
      child: ElevatedButton.icon(
        icon: Icon(icon, color: Colors.white),
        label: Text(
          text,
          style: TextStyle(
            color: Colors.white,
            fontSize: 16,
          ),
        ),
        style: ElevatedButton.styleFrom(
          backgroundColor: Colors.white.withOpacity(0.2),
          padding: EdgeInsets.symmetric(vertical: 15),
          shape: RoundedRectangleBorder(
            borderRadius: BorderRadius.circular(10),
            side: BorderSide(
              color: Colors.white.withOpacity(0.3),
              width: 1,
            ),
          ),
        ),
        onPressed: () {
          Navigator.pushNamed(context, route);
        },
      ),
    );
  }
}

// Página de FAQ Mejorada

// Página de Registro Mejorada
class RegisterPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      extendBodyBehindAppBar: true,
      appBar: AppBar(
        backgroundColor: Colors.transparent,
        elevation: 0,
        title: Text(
          "Registro",
          style: TextStyle(
            color: Colors.white,
            fontWeight: FontWeight.bold,
          ),
        ),
        iconTheme: IconThemeData(color: Colors.white),
      ),
      body: Stack(
        children: [
          // Fondo con gradiente
          Container(
            decoration: BoxDecoration(
              gradient: LinearGradient(
                begin: Alignment.topRight,
                end: Alignment.bottomLeft,
                colors: [
                  Color(0xFF7B1FA2),
                  Color(0xFF9C27B0),
                  Color(0xFFBA68C8),
                ],
              ),
            ),
          ),
          
          // Formas decorativas
          Positioned(
            top: 70,
            right: -40,
            child: Container(
              width: 180,
              height: 180,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.2),
                borderRadius: BorderRadius.circular(90),
              ),
            ),
          ),
          
          Positioned(
            bottom: -60,
            left: -30,
            child: Container(
              width: 220,
              height: 220,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.1),
                borderRadius: BorderRadius.circular(110),
              ),
            ),
          ),
          
          // Contenido principal con blur
          SafeArea(
            child: Center(
              child: SingleChildScrollView(
                padding: EdgeInsets.all(20),
                child: ClipRRect(
                  borderRadius: BorderRadius.circular(20),
                  child: BackdropFilter(
                    filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                    child: Container(
                      padding: EdgeInsets.all(30),
                      decoration: BoxDecoration(
                        color: Colors.white.withOpacity(0.2),
                        borderRadius: BorderRadius.circular(20),
                        border: Border.all(
                          color: Colors.white.withOpacity(0.2),
                          width: 1.5,
                        ),
                        boxShadow: [
                          BoxShadow(
                            color: Colors.black.withOpacity(0.1),
                            blurRadius: 20,
                            spreadRadius: 5,
                          ),
                        ],
                      ),
                      child: Column(
                        mainAxisSize: MainAxisSize.min,
                        children: [
                          Text(
                            "Crear Cuenta",
                            style: TextStyle(
                              fontSize: 24,
                              fontWeight: FontWeight.bold,
                              color: Colors.white,
                            ),
                          ),
                          SizedBox(height: 30),
                          
                          // Campo nombre
                          _buildTextField(
                            hint: 'Nombre',
                            icon: Icons.person_outline,
                          ),
                          SizedBox(height: 15),
                          
                          // Campo correo
                          _buildTextField(
                            hint: 'Correo electrónico',
                            icon: Icons.email_outlined,
                          ),
                          SizedBox(height: 15),
                          
                          // Campo contraseña
                          _buildTextField(
                            hint: 'Contraseña',
                            icon: Icons.lock_outline,
                            isPassword: true,
                          ),
                          SizedBox(height: 15),
                          
                          // Campo confirmar contraseña
                          _buildTextField(
                            hint: 'Confirmar contraseña',
                            icon: Icons.lock_outline,
                            isPassword: true,
                          ),
                          SizedBox(height: 30),
                          
                          // Botón de registro
                          ElevatedButton(
                            style: ElevatedButton.styleFrom(
                              foregroundColor: Colors.white,
                              backgroundColor: Colors.white.withOpacity(0.3),
                              minimumSize: Size(double.infinity, 50),
                              shape: RoundedRectangleBorder(
                                borderRadius: BorderRadius.circular(10),
                              ),
                            ),
                            child: Text(
                              "REGISTRARSE",
                              style: TextStyle(
                                fontSize: 16,
                                fontWeight: FontWeight.bold,
                              ),
                            ),
                            onPressed: () {
                              Navigator.pushReplacementNamed(context, "/main");
                            },
                          ),
                          SizedBox(height: 15),
                          
                          // Botón de cancelar
                          TextButton(
                            style: TextButton.styleFrom(
                              foregroundColor: Colors.white,
                            ),
                            child: Text("Cancelar"),
                            onPressed: () {
                              Navigator.pushReplacementNamed(context, "/main");
                            },
                          ),
                        ],
                      ),
                    ),
                  ),
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
  
  // Método para crear campos de texto con estilo
  Widget _buildTextField({
    required String hint,
    required IconData icon,
    bool isPassword = false,
  }) {
    return TextField(
      obscureText: isPassword,
      style: TextStyle(color: Colors.white),
      decoration: InputDecoration(
        hintText: hint,
        hintStyle: TextStyle(color: Colors.white70),
        prefixIcon: Icon(icon, color: Colors.white70),
        enabledBorder: OutlineInputBorder(
          borderRadius: BorderRadius.circular(10),
          borderSide: BorderSide(color: Colors.white38),
        ),
        focusedBorder: OutlineInputBorder(
          borderRadius: BorderRadius.circular(10),
          borderSide: BorderSide(color: Colors.white),
        ),
        filled: true,
        fillColor: Colors.white.withOpacity(0.1),
      ),
    );
  }
}

// Página de Calculadora Mejorada

class CalculatorPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      extendBodyBehindAppBar: true,
      appBar: AppBar(
        backgroundColor: Colors.transparent,
        elevation: 0,
        title: Text(
          "Calculadora",
          style: TextStyle(
            color: Colors.white,
            fontWeight: FontWeight.bold,
          ),
        ),
        iconTheme: IconThemeData(color: Colors.white),
      ),
      body: Stack(
        children: [
          // Fondo con gradiente
          Container(
            decoration: BoxDecoration(
              gradient: LinearGradient(
                begin: Alignment.topLeft,
                end: Alignment.bottomRight,
                colors: [
                  Color(0xFFE63946),
                  Color(0xFFD00000),
                  Color(0xFF9D0208),
                ],
              ),
            ),
          ),
          
          // Formas decorativas
          Positioned(
            top: 70,
            left: -30,
            child: Container(
              width: 160,
              height: 160,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.2),
                borderRadius: BorderRadius.circular(80),
              ),
            ),
          ),
          
          Positioned(
            bottom: -40,
            right: -20,
            child: Container(
              width: 180,
              height: 180,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.1),
                borderRadius: BorderRadius.circular(90),
              ),
            ),
          ),
          
          // Contenido principal
          SafeArea(
            child: Padding(
              padding: EdgeInsets.all(16),
              child: Column(
                children: [
                  // Display de la calculadora
                  ClipRRect(
                    borderRadius: BorderRadius.circular(20),
                    child: BackdropFilter(
                      filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                      child: Container(
                        width: double.infinity,
                        padding: EdgeInsets.all(20),
                        decoration: BoxDecoration(
                          color: Colors.white.withOpacity(0.2),
                          borderRadius: BorderRadius.circular(20),
                          border: Border.all(
                            color: Colors.white.withOpacity(0.2),
                            width: 1.5,
                          ),
                        ),
                        child: Column(
                          children: [
                            // Mostrar operación actual (opcional)
                            Container(
                              alignment: Alignment.centerRight,
                              padding: EdgeInsets.symmetric(vertical: 8),
                              child: Text(
                                "123+45",
                                style: TextStyle(
                                  fontSize: 18,
                                  color: Colors.white.withOpacity(0.7),
                                ),
                              ),
                            ),
                            // Mostrar resultado
                            Container(
                              alignment: Alignment.centerRight,
                              padding: EdgeInsets.symmetric(vertical: 8),
                              child: Text(
                                "168",
                                style: TextStyle(
                                  fontSize: 48,
                                  fontWeight: FontWeight.bold,
                                  color: Colors.white,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  
                  SizedBox(height: 20),
                  
                  // Teclado de la calculadora
                  Expanded(
                    child: ClipRRect(
                      borderRadius: BorderRadius.circular(20),
                      child: BackdropFilter(
                        filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                        child: Container(
                          padding: EdgeInsets.all(15),
                          decoration: BoxDecoration(
                            color: Colors.white.withOpacity(0.15),
                            borderRadius: BorderRadius.circular(20),
                            border: Border.all(
                              color: Colors.white.withOpacity(0.2),
                              width: 1.5,
                            ),
                          ),
                          child: Column(
                            children: [
                              Expanded(
                                child: Row(
                                  children: [
                                    _buildCalculatorButton("7"),
                                    _buildCalculatorButton("8"),
                                    _buildCalculatorButton("9"),
                                    _buildOperatorButton("÷"),
                                  ],
                                ),
                              ),
                              Expanded(
                                child: Row(
                                  children: [
                                    _buildCalculatorButton("4"),
                                    _buildCalculatorButton("5"),
                                    _buildCalculatorButton("6"),
                                    _buildOperatorButton("×"),
                                  ],
                                ),
                              ),
                              Expanded(
                                child: Row(
                                  children: [
                                    _buildCalculatorButton("1"),
                                    _buildCalculatorButton("2"),
                                    _buildCalculatorButton("3"),
                                    _buildOperatorButton("-"),
                                  ],
                                ),
                              ),
                              Expanded(
                                child: Row(
                                  children: [
                                    _buildFunctionButton("C"),
                                    _buildCalculatorButton("0"),
                                    _buildFunctionButton("="),
                                    _buildOperatorButton("+"),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ),
                  
                  SizedBox(height: 20),
                  
                  // Botón para volver al menú
                  ClipRRect(
                    borderRadius: BorderRadius.circular(15),
                    child: BackdropFilter(
                      filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                      child: Container(
                        width: double.infinity,
                        height: 50,
                        decoration: BoxDecoration(
                          color: Colors.white.withOpacity(0.25),
                          borderRadius: BorderRadius.circular(15),
                          border: Border.all(
                            color: Colors.white.withOpacity(0.2),
                            width: 1.5,
                          ),
                        ),
                        child: ElevatedButton.icon(
                          style: ElevatedButton.styleFrom(
                            backgroundColor: Colors.transparent,
                            foregroundColor: Colors.white,
                            elevation: 0,
                            shape: RoundedRectangleBorder(
                              borderRadius: BorderRadius.circular(15),
                            ),
                          ),
                          icon: Icon(Icons.home_outlined),
                          label: Text(
                            "Volver al Menú Principal",
                            style: TextStyle(
                              fontSize: 16,
                              fontWeight: FontWeight.w500,
                            ),
                          ),
                          onPressed: () {
                            Navigator.pushReplacementNamed(context, "/main");
                          },
                        ),
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }
  
  // Método para botones numéricos
  Widget _buildCalculatorButton(String text) {
    return Expanded(
      child: Padding(
        padding: EdgeInsets.all(4),
        child: ClipRRect(
          borderRadius: BorderRadius.circular(15),
          child: BackdropFilter(
            filter: ImageFilter.blur(sigmaX: 5, sigmaY: 5),
            child: Container(
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.15),
                borderRadius: BorderRadius.circular(15),
                border: Border.all(
                  color: Colors.white.withOpacity(0.2),
                  width: 1,
                ),
              ),
              child: TextButton(
                style: TextButton.styleFrom(
                  foregroundColor: Colors.white,
                  padding: EdgeInsets.all(0),
                  backgroundColor: Colors.transparent,
                ),
                onPressed: () {},  // No hace nada
                child: Text(
                  text,
                  style: TextStyle(
                    fontSize: 24,
                    fontWeight: FontWeight.w400,
                  ),
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
  
  // Método para botones de operadores
  Widget _buildOperatorButton(String text) {
    return Expanded(
      child: Padding(
        padding: EdgeInsets.all(4),
        child: ClipRRect(
          borderRadius: BorderRadius.circular(15),
          child: BackdropFilter(
            filter: ImageFilter.blur(sigmaX: 5, sigmaY: 5),
            child: Container(
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.25),
                borderRadius: BorderRadius.circular(15),
                border: Border.all(
                  color: Colors.white.withOpacity(0.2),
                  width: 1,
                ),
              ),
              child: TextButton(
                style: TextButton.styleFrom(
                  foregroundColor: Colors.white,
                  backgroundColor: Colors.transparent,
                  padding: EdgeInsets.all(0),
                ),
                onPressed: () {},  // No hace nada
                child: Text(
                  text,
                  style: TextStyle(
                    fontSize: 28,
                    fontWeight: FontWeight.bold,
                  ),
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
  
  // Método para botones de función (C e =)
  Widget _buildFunctionButton(String text) {
    Color bgColor = text == "C" 
        ? Colors.red.withOpacity(0.3) 
        : Colors.green.withOpacity(0.3);
        
    return Expanded(
      child: Padding(
        padding: EdgeInsets.all(4),
        child: ClipRRect(
          borderRadius: BorderRadius.circular(15),
          child: BackdropFilter(
            filter: ImageFilter.blur(sigmaX: 5, sigmaY: 5),
            child: Container(
              decoration: BoxDecoration(
                color: bgColor,
                borderRadius: BorderRadius.circular(15),
                border: Border.all(
                  color: Colors.white.withOpacity(0.2),
                  width: 1,
                ),
              ),
              child: TextButton(
                style: TextButton.styleFrom(
                  foregroundColor: Colors.white,
                  backgroundColor: Colors.transparent,
                  padding: EdgeInsets.all(0),
                ),
                onPressed: () {},  // No hace nada
                child: Text(
                  text,
                  style: TextStyle(
                    fontSize: 24,
                    fontWeight: FontWeight.bold,
                  ),
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
}

// Clase para elementos FAQ
// Página de FAQ Mejorada
class FAQPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      extendBodyBehindAppBar: true,
      appBar: AppBar(
        backgroundColor: Colors.transparent,
        elevation: 0,
        title: Text(
          "Preguntas Frecuentes",
          style: TextStyle(
            color: Colors.white,
            fontWeight: FontWeight.bold,
          ),
        ),
        iconTheme: IconThemeData(color: Colors.white),
      ),
      body: Stack(
        children: [
          // Fondo con gradiente
          Container(
            decoration: BoxDecoration(
              gradient: LinearGradient(
                begin: Alignment.topLeft,
                end: Alignment.bottomRight,
                colors: [
                  Color(0xFFF08700),
                  Color(0xFFD95D39),
                  Color(0xFFF18F01),
                ],
              ),
            ),
          ),
          
          // Formas decorativas
          Positioned(
            top: -30,
            right: -30,
            child: Container(
              width: 150,
              height: 150,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.2),
                borderRadius: BorderRadius.circular(75),
              ),
            ),
          ),
          
          Positioned(
            bottom: -50,
            left: -25,
            child: Container(
              width: 180,
              height: 180,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.1),
                borderRadius: BorderRadius.circular(90),
              ),
            ),
          ),
          
          // Lista de preguntas
          SafeArea(
            child: Padding(
              padding: EdgeInsets.fromLTRB(16, 16, 16, 80), // Añadir espacio para el botón flotante
              child: ClipRRect(
                borderRadius: BorderRadius.circular(15),
                child: BackdropFilter(
                  filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                  child: Container(
                    decoration: BoxDecoration(
                      color: Colors.white.withOpacity(0.15),
                      borderRadius: BorderRadius.circular(15),
                      border: Border.all(
                        color: Colors.white.withOpacity(0.2),
                        width: 1.5,
                      ),
                    ),
                    child: ListView.builder(
                      itemCount: faqList.length,
                      itemBuilder: (context, index) {
                        return Padding(
                          padding: EdgeInsets.symmetric(vertical: 4, horizontal: 8),
                          child: ClipRRect(
                            borderRadius: BorderRadius.circular(10),
                            child: BackdropFilter(
                              filter: ImageFilter.blur(sigmaX: 5, sigmaY: 5),
                              child: ExpansionTile(
                                collapsedBackgroundColor: Colors.white.withOpacity(0.1),
                                backgroundColor: Colors.white.withOpacity(0.2),
                                shape: RoundedRectangleBorder(
                                  borderRadius: BorderRadius.circular(10),
                                ),
                                collapsedShape: RoundedRectangleBorder(
                                  borderRadius: BorderRadius.circular(10),
                                ),
                                title: Text(
                                  faqList[index].question,
                                  style: TextStyle(
                                    color: Colors.white,
                                    fontWeight: FontWeight.bold,
                                    fontSize: 16,
                                  ),
                                ),
                                iconColor: Colors.white,
                                collapsedIconColor: Colors.white70,
                                children: [
                                  Padding(
                                    padding: EdgeInsets.all(16),
                                    child: Text(
                                      faqList[index].answer,
                                      style: TextStyle(
                                        fontSize: 15.0,
                                        color: Colors.white.withOpacity(0.9),
                                      ),
                                    ),
                                  ),
                                ],
                              ),
                            ),
                          ),
                        );
                      },
                    ),
                  ),
                ),
              ),
            ),
          ),
          
          // Botón flotante con efecto de vidrio
          Positioned(
            bottom: 20,
            right: 20,
            child: ClipRRect(
              borderRadius: BorderRadius.circular(30),
              child: BackdropFilter(
                filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
                child: Container(
                  decoration: BoxDecoration(
                    color: Colors.white.withOpacity(0.3),
                    borderRadius: BorderRadius.circular(30),
                    border: Border.all(
                      color: Colors.white.withOpacity(0.2),
                      width: 1.5,
                    ),
                  ),
                  child: FloatingActionButton(
                    backgroundColor: Colors.transparent,
                    elevation: 0,
                    highlightElevation: 0,
                    child: Icon(Icons.home, color: Colors.white),
                    onPressed: () {
                      Navigator.pushReplacementNamed(context, "/main");
                    },
                  ),
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
}

// Clase para elementos FAQ
class FAQItem {
  final String question;
  final String answer;
  FAQItem({required this.question, required this.answer});
}

// Lista de preguntas frecuentes (ahora con 10 preguntas)
final List<FAQItem> faqList = [
  FAQItem(
    question: '¿Cómo puedo cambiar mi contraseña?',
    answer: 'Para cambiar tu contraseña, ve a la sección de configuración y busca la opción "Cambiar contraseña".',
  ),
  FAQItem(
    question: '¿Cuáles son los métodos de pago aceptados?',
    answer: 'Aceptamos tarjetas de crédito, transferencias bancarias y pagos en efectivo en nuestras sucursales.',
  ),
  FAQItem(
    question: '¿Cómo puedo contactar al soporte técnico?',
    answer: 'Puedes contactar a nuestro equipo de soporte a través del correo electrónico soporte@ejemplo.com o llamando al número 555-123-4567.',
  ),
  FAQItem(
    question: '¿Cuál es el horario de atención?',
    answer: 'Nuestro horario de atención es de lunes a viernes de 9:00 AM a 6:00 PM.',
  ),
  FAQItem(
    question: '¿Cómo puedo cancelar mi suscripción?',
    answer: 'Para cancelar tu suscripción, ingresa a tu perfil, selecciona "Suscripciones" y haz clic en "Cancelar suscripción". Recibirás un correo de confirmación cuando el proceso se complete.',
  ),
  FAQItem(
    question: '¿Qué hago si olvidé mi contraseña?',
    answer: 'En la pantalla de inicio de sesión, haz clic en "¿Olvidaste tu contraseña?" y sigue las instrucciones para restablecerla a través de tu correo electrónico registrado.',
  ),
  FAQItem(
    question: '¿Cuánto tiempo tarda el envío de productos?',
    answer: 'El tiempo de envío estándar es de 3 a 5 días hábiles dentro del país. Para envíos internacionales, el plazo estimado es de 7 a 14 días hábiles, dependiendo del destino.',
  ),
  FAQItem(
    question: '¿Puedo cambiar la dirección de entrega después de realizar mi pedido?',
    answer: 'Sí, puedes modificar la dirección de entrega hasta 24 horas después de realizar tu pedido. Para hacerlo, contacta a nuestro servicio al cliente con tu número de pedido.',
  ),
  FAQItem(
    question: '¿Ofrecen garantía en sus productos?',
    answer: 'Sí, todos nuestros productos cuentan con garantía de 12 meses contra defectos de fabricación. Algunos artículos premium tienen garantía extendida de hasta 3 años.',
  ),
  FAQItem(
    question: '¿Tienen política de devoluciones?',
    answer: 'Sí, aceptamos devoluciones dentro de los primeros 30 días posteriores a la compra. El producto debe estar en su empaque original y en perfectas condiciones. Los gastos de envío para devoluciones corren por cuenta del cliente, excepto en casos de productos defectuosos.',
  ),
];
```
