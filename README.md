# checkpoint-node.js


// hello-world.js  
console.log("HELLO WORLD");  
2. Créer un serveur
Créer un fichier nommé server.js et écrire le programme suivant :

// server.js  
const http = require("http");  

const server = http.createServer((req, res) => {  
  res.writeHead(200, { "Content-Type": "text/html" });  
  res.end('<h1>Hello Node !!!!</h1>\n');  
});  

server.listen(3000, () => {  
  console.log("Server running at http://localhost:3000/");  
});  
3. Créer un fichier welcome.txt et lire son contenu
Créer un fichier nommé file-handler.js et écrire le programme suivant :

// file-handler.js  
const fs = require("fs");  

// Écrire dans le fichier welcome.txt  
fs.writeFile("welcome.txt", "Hello Node", (err) => {  
  if (err) throw err;  
  console.log("welcome.txt has been created!");  

  // Lire le fichier hello.txt  
  fs.readFile("welcome.txt", "utf8", (err, data) => {  
    if (err) throw err;  
    console.log(data);  
  });  
});  
4. Créer un générateur de mots de passe
Créer un fichier nommé password-generator.js et écrire le programme suivant :

// password-generator.js  
const generatePassword = require("generate-password");  

const password = generatePassword.generate({  
  length: 10,  
  numbers: true,  
  symbols: true  
});  

console.log("Generated Password: ", password);  
Assurez-vous d'installer le module generate-password :

npm install generate-password  
5. Créer un fichier pour l'envoi d'e-mails
Créer un fichier nommé email-sender.js et écrire le programme suivant :

// email-sender.js  
const nodemailer = require("nodemailer");  

const transporter = nodemailer.createTransport({  
  service: 'gmail', // ou votre service préféré  
  auth: {  
    user: 'votre-email@gmail.com', // Remplacez par votre adresse email  
    pass: 'votre-mot-de-passe' // Remplacez par votre mot de passe  
  }  
});  

const mailOptions = {  
  from: 'votre-email@gmail.com',  
  to: 'destinataire@example.com', // Remplacez par l'email du destinataire  
  subject: 'Hello from Node.js',  
  text: 'This is a test email sent from Node.js!' // Corps de l'email  
};  

transporter.sendMail(mailOptions, (error, info) => {  
  if (error) {  
    return console.log(error);  
  }  
  console.log('Email sent: ' + info.response);  
});  
Assurez-vous d'installer le module nodemailer :

npm install nodemailer  
