# 🚀 Yilin Lyu's Personal Homepage

Welcome to my digital playground! 👋

## 🌟 What's This?

This is my personal academic homepage built with Jekyll, showcasing my research interests, projects, and professional journey. Think of it as my digital business card, but way cooler! 

## 🎯 Key Features

### 🧠 Interactive Interest Network
My favorite feature! An interactive D3.js visualization of my research interests and their connections. It's like a mind map, but animated and zoomable!

- **Hierarchical Structure**: Research → Machine Learning → Time Series Analysis → Mamba
- **Cross-domain Connections**: See how Python connects to Process Mining, or how Ada relates to Cybersecurity
- **Dynamic Zoom**: Explore the network at different scales
- **Color-coded Nodes**: Each level has its own visual identity

### 📚 Academic Portfolio
- **Publications**: My research papers and contributions
- **Projects**: From development clubs to VPA systems
- **Industry Experience**: Full-time roles and internships
- **News & Updates**: Latest happenings in my academic journey

## 🛠️ Tech Stack

- **Jekyll**: Static site generation
- **D3.js**: Interactive data visualization
- **YAML**: Data-driven interest structure
<<<<<<< HEAD
- **GitHub Pages**: Hosting and deployment

## 🎨 Design Philosophy

- **Clean & Modern**: Minimalist design with focus on content
- **Responsive**: Works on desktop, tablet, and mobile
- **Accessible**: High contrast and readable typography
- **Fast**: Optimized for quick loading

## 🔧 How It Works

### Interest Network Structure
The interest network uses a hierarchical YAML structure:

```yaml
- id: Research
  color: "#1E90FF"
  children:
    - id: Machine Learning
      children:
        - id: Time Series Analysis
          children:
            - id: Mamba
```

### Cross-domain Connections
Special connections between different domains are defined in JavaScript:

```javascript
{source: 'Python', target: 'Machine Learning'},
{source: 'Ada', target: 'Cybersecurity'}
```

## 🚀 Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/lvyl9909/lvyl9909.github.io.git
   ```

2. **Install dependencies**
   ```bash
   bundle install
   ```

3. **Run locally**
   ```bash
   bundle exec jekyll serve
   ```

4. **Visit** `http://localhost:4000`

## 📊 Adding New Interests

Want to add a new research interest? It's super easy!

1. **Edit** `_data/interests.yml`
2. **Add** your new node in the right place
3. **Restart** Jekyll server
4. **Done!** The visualization updates automatically

## 🤝 Contributing

Found a bug? Want to suggest an improvement? Feel free to:
- Open an issue
- Submit a pull request
- Reach out directly

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

**Built with ❤️ and lots of ☕**
