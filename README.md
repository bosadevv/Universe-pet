# 🐾 Universe Pet - Sistema Completo para Gestão de Pets

<div align="center">
  
  ![Universe Pet Logo](https://img.shields.io/badge/Universe-Pet-ffbcb7?style=for-the-badge&logo=github&logoColor=white)
  
  [![PHP Version](https://img.shields.io/badge/PHP-8.0+-777BB4?style=flat-square&logo=php&logoColor=white)](https://php.net)
  [![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://mysql.com)
  [![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://javascript.com)
  [![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
  
  <h3>🐶 Seu assistente completo para cuidar do seu melhor amigo 🐱</h3>
  
  [🔗 Acesse o Projeto](#) • 
  [📋 Documentação](#) • 
  [🐛 Reportar Bug](#) • 
  [✨ Solicitar Feature](#)
  
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%">
  
</div>

## 📸 Preview do Sistema

<div align="center">
  
  ### 📱 Versão Desktop
  
  ![Desktop Preview](https://via.placeholder.com/800x400/ffbcb7/ffffff?text=Universe+Pet+Desktop)
  
  ### 📱 Versão Mobile
  
  ![Mobile Preview](https://via.placeholder.com/300x600/ffbcb7/ffffff?text=Universe+Pet+Mobile)
  
</div>

## 🌟 Sobre o Projeto

O **Universe Pet** é um sistema web completo desenvolvido para ajudar tutores de pets a gerenciarem todos os aspectos da vida de seus animais de estimação. Com uma interface amigável e responsiva, o sistema oferece ferramentas essenciais para cuidar da saúde, bem-estar e segurança do seu pet.

### 🎯 Principais Funcionalidades

| Funcionalidade | Descrição |
|----------------|-----------|
| 📸 **Galeria** | Armazene e organize fotos do seu pet |
| 📅 **Agendamentos** | Gerencie consultas, vacinas, banhos e mais |
| 🆘 **Pets Perdidos** | Divulgue e encontre pets desaparecidos |
| ❤️ **Doação** | Anuncie pets para adoção responsável |
| 📚 **Tutorial** | Guias e dicas sobre cuidados com pets |
| 🏥 **Pet Shops** | Encontre pet shops próximos |
| 📝 **Blog** | Artigos e novidades sobre o mundo pet |
| 📊 **Aprenda** | Conteúdo educativo sobre saúde animal |

## 🚀 Tecnologias Utilizadas

<div align="center">
  
| | Tecnologia | Versão |
|--|------------|--------|
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" width="20"> | **PHP** | 8.0+ |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" width="20"> | **MySQL** | 8.0 |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" width="20"> | **JavaScript** | ES6+ |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" width="20"> | **HTML5** | - |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" width="20"> | **CSS3** | - |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" width="20"> | **VS Code** | - |

</div>

## ✨ Destaques do Sistema

### 📅 **Sistema de Agendamentos Inteligente**
- ✅ Tipos padronizados: Medicamento, Vacina, Anti pulgas, Vermífugo, Consulta, Exame, Peso, Banho, Tosa, Higiene e Outros
- ✅ Upload de imagens para medicamentos e receitas
- ✅ Filtros por categoria
- ✅ Cards expansivos com informações detalhadas
- ✅ Pop-up animado de carregamento
- ✅ Totalmente responsivo

### 🎨 **Design Moderno e Acessível**
- ✅ Interface clean e intuitiva
- ✅ Cores suaves e agradáveis
- ✅ Animações suaves
- ✅ Menu lateral estiloso
- ✅ Modais personalizados
- ✅ Badges e indicadores visuais

### 📱 **Responsividade Completa**
- ✅ Adaptação perfeita para celulares
- ✅ Cards que se reorganizam
- ✅ Menu hambúrguer em telas pequenas
- ✅ Filtros com scroll horizontal
- ✅ Imagens responsivas

## 🛠️ Estrutura do Banco de Dados

```sql
-- Tabela de usuários
CREATE TABLE usuarios (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    senha VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tabela de pets
CREATE TABLE pets (
    id INT PRIMARY KEY AUTO_INCREMENT,
    usuario_id INT NOT NULL,
    nome VARCHAR(50) NOT NULL,
    especie VARCHAR(30),
    raca VARCHAR(50),
    data_nascimento DATE,
    foto VARCHAR(255),
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id)
);

-- Tabela de agendamentos
CREATE TABLE agendamentos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    usuario_id INT NOT NULL,
    pet_id INT NOT NULL,
    titulo VARCHAR(50) NOT NULL,
    subtitulo VARCHAR(100),
    descricao TEXT,
    data DATE NOT NULL,
    hora TIME NOT NULL,
    imagem VARCHAR(500),
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id),
    FOREIGN KEY (pet_id) REFERENCES pets(id)
);
