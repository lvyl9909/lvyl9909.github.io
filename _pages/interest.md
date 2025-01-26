---
layout: page
title: Interest
permalink: /interest/
nav: true
nav_order: 5
---

Below is my interest network🌐. Zoom-in to explore it!

<svg id="graph" width="1000" height="800"></svg>

<script src="https://d3js.org/d3.v7.min.js"></script>

<script>const data = {
  nodes: [
    // 第一层级
    {id: 'Research', group: 'Research', color: '#1E90FF', r: 200},
    {id: 'Industry', group: 'Industry', color: '#FFD700', r: 200},
    {id: 'Programming', group: 'Programming', color: '#8A2BE2', r: 200},
    {id: 'Software Tech', group: 'Software Tech', color: '#FF6347', r: 200},
    // 第二层级 - Research的子类
    {id: 'Process Mining', group: 'Process Mining', parent: 'Research'},
    {id: 'Cybersecurity', group: 'Cybersecurity', parent: 'Research'},
    {id: 'Computer Modeling', group: 'Computer Modeling', parent: 'Research'},
    {id: 'Machine Learning', group: 'Machine Learning', parent: 'Research'},
    {id: 'Knowledge Representation and Reasoning', group: 'Knowledge Representation and Reasoning', parent: 'Research'},
    {id: 'Logic Education', group: 'Logic Education', parent: 'Research'},

    // 第二层级 - Industry的子类
    {id: 'Network Security', group: 'Network Security', parent: 'Industry'},
    {id: 'Web Application', group: 'Web Application', parent: 'Industry'},
    {id: 'Maven', group: 'Maven', parent: 'Web Application'},

    // 第二层级 - Programming的子类
    {id: 'C++', group: 'C++', parent: 'Programming'},
    {id: 'Ada', group: 'Ada', parent: 'Programming'},
    {id: 'Alloy', group: 'Alloy', parent: 'Programming'},
    {id: 'Python', group: 'Python', parent: 'Programming'},
    {id: 'Java', group: 'Java', parent: 'Programming'},
    {id: 'Javascript', group: 'Javascript', parent: 'Programming'},
    {id: 'HTML', group: 'HTML', parent: 'Programming'},
    {id: 'Typescript', group: 'Typescript', parent: 'Programming'},
    {id: 'PHP', group: 'PHP', parent: 'Programming'},
    {id: 'MATLAB', group: 'MATLAB', parent: 'Programming'},
    // 第二层级 - Software Tech的子类
    {id: 'Testing', group: 'Software Testing', parent: 'Software Tech'},
    {id: 'Project Management', group: 'Software Project Management', parent: 'Software Tech'},
    {id: 'Architecture', group: 'Software Architecture', parent: 'Software Tech'},
    {id: 'Framework', group: 'Framework', parent: 'Software Tech'},
    //第三层级 - Machine Learning的子类
    {id: 'Generative Adversarial Networks', group: 'Generative Adversarial Networks', parent: 'Machine Learning'},
    {id: 'Graph Neural Networks', group: 'Graph Neural Networks', parent: 'Machine Learning'},
    {id: 'Time Series Analysis', group: 'Time Series Analysis', parent: 'Machine Learning'}, 
    {id: 'Clustering', group: 'Clustering', parent: 'Machine Learning'}, 
    //第四层级 - Sequence Model的子类
    {id: 'RNN', group: 'RNN', parent: 'Time Series Analysis'},    
    {id: 'LSTM', group: 'LSTM', parent: 'Time Series Analysis'},
    {id: 'Transformer', group: 'Transformer', parent: 'Time Series Analysis'},
    {id: 'Mamba', group: 'Mamba', parent: 'Time Series Analysis'},   
    // 第三层级 - Process Mining的子类
    {id: 'Process Discovery', group: 'Process Discovery', parent: 'Process Mining'},
    {id: 'Process Prediction', group: 'Process Prediction', parent: 'Process Mining'},
    {id: 'Conformance Checking', group: 'Conformance Checking', parent: 'Process Mining'},
    {id: 'Anomaly Detection', group: 'Anomaly Detection', parent: 'Process Mining'},
    // 第四层级 - Conformance Checking的子类
    {id: 'Sampling Approximation', group: 'Sampling Approximation', parent: 'Conformance Checking'},
    {id: 'RNN-based Approximation', group: 'RNN-based Approximation', parent: 'Conformance Checking'},
    {id: 'Stochastic Conformance Checking', group: 'Stochastic Conformance Checking', parent: 'Conformance Checking'},
    // 第三层级 - Software Testing的子类
    {id: 'Fuzzing', group: 'Fuzzing', parent: 'Testing'},
    {id: 'V model', group: 'V model', parent: 'Testing'},
    // 第三层级 - Framework的子类
    {id: 'React', group: 'React', parent: 'Framework'},
    {id: 'Vue', group: 'Vue', parent: 'Framework'},
    {id: 'Django', group: 'Django', parent: 'Framework'},
    {id: 'Servlet', group: 'Servlet', parent: 'Framework'},
    {id: 'Next.js', group: 'Next.js', parent: 'Framework'},
    {id: 'TensorFlow', group: 'TensorFlow', parent: 'Framework'},
    {id: 'PyTorch', group: 'PyTorch', parent: 'Framework'},
    // 第四层级 - Fuzzing的子类
    {id: 'AFLNet', group: 'AFLNet', parent: 'Fuzzing'},
    {id: 'LibFuzzer', group: 'LibFuzzer', parent: 'Fuzzing'}
  ],

  links: [
      // 第一层级的连接
      {source: 'Research', target: 'Process Mining'},
      {source: 'Research', target: 'Cybersecurity'},
      {source: 'Research', target: 'Computer Modeling'},
      {source: 'Research', target: 'Machine Learning'},
      
      {source: 'Industry', target: 'Network Security'},
      {source: 'Industry', target: 'Web Application'},
      {source: 'Industry', target: 'Project Management'},
      {source: 'Web Application', target: 'Maven'},
      {source: 'Java', target: 'Maven'},   

      {source: 'Programming', target: 'C++'},
      {source: 'Programming', target: 'Ada'},
      {source: 'Programming', target: 'Alloy'},
      {source: 'Programming', target: 'Python'},
      {source: 'Programming', target: 'Java'},
      {source: 'Programming', target: 'Javascript'},
      {source: 'Programming', target: 'HTML'},
      {source: 'Programming', target: 'Typescript'},
      {source: 'Programming', target: 'PHP'},
      {source: 'Programming', target: 'MATLAB'},
    
      {source: 'Software Tech', target: 'Testing'},
      {source: 'Software Tech', target: 'Project Management'},
      {source: 'Software Tech', target: 'Architecture'},
      {source: 'Software Tech', target: 'Framework'},

      // 第二层级 - Machine Learning的子类
      {source: 'Machine Learning', target: 'Generative Adversarial Networks'},
      {source: 'Machine Learning', target: 'Graph Neural Networks'},
      {source: 'Machine Learning', target: 'Time Series Analysis'},
      {source: 'Machine Learning', target: 'Clustering'},
    
      // 第三层级 - Time Series Analysis的子类
      {source: 'Time Series Analysis', target: 'RNN'},
      {source: 'Time Series Analysis', target: 'LSTM'},
      {source: 'Time Series Analysis', target: 'Transformer'},
      {source: 'Time Series Analysis', target: 'Mamba'},
    
      // 第三层级 - Process Mining的子类
      {source: 'Process Mining', target: 'Process Discovery'},
      {source: 'Process Mining', target: 'Process Prediction'},
      {source: 'Process Mining', target: 'Conformance Checking'},
      {source: 'Process Mining', target: 'Anomaly Detection'},
      {source: 'Graph Neural Networks', target: 'Anomaly Detection'},
      {source: 'Clustering', target: 'Process Discovery'},
      {source: 'Clustering', target: 'Conformance Checking'},
      {source: 'RNN', target: 'RNN-based Approximation'},
      {source: 'Mamba', target: 'RNN-based Approximation'},

    
      // 第四层级 - Conformance Checking的子类
      {source: 'Conformance Checking', target: 'Sampling Approximation'},
      {source: 'Conformance Checking', target: 'RNN-based Approximation'},
      {source: 'Conformance Checking', target: 'Stochastic Conformance Checking'},
    
      // 第三层级 - Testing的子类
      {source: 'Testing', target: 'Fuzzing'},
      {source: 'Testing', target: 'V model'},
     // 第三层级 - Framework的子类
      {source: 'Framework', target: 'React'},
      {source: 'Framework', target: 'Vue'},
      {source: 'Framework', target: 'Django'},
      {source: 'Framework', target: 'Servlet'},
      {source: 'Framework', target: 'Next.js'},
      {source: 'Framework', target: 'TensorFlow'},
      {source: 'Framework', target: 'PyTorch'},
      {source: 'Python', target: 'Django'},
      {source: 'Vue', target: 'HTML'},
      {source: 'React', target: 'HTML'},
      {source: 'React', target: 'Javascript'},
      {source: 'React', target: 'Typescript'},
      {source: 'Servlet', target: 'Java'},
      {source: 'PHP', target: 'Project Management'},
    
      // 第四层级 - Fuzzing的子类
      {source: 'Fuzzing', target: 'AFLNet'},
      {source: 'Fuzzing', target: 'LibFuzzer'},
    
      // **领域间的技术相关性连接**
      // Time Series Analysis & Machine Learning
      {source: 'Time Series Analysis', target: 'Generative Adversarial Networks'},
      {source: 'Time Series Analysis', target: 'Graph Neural Networks'},
      {source: 'Time Series Analysis', target: 'Clustering'},
    
      // Machine Learning 与 Frameworks 相关性
      {source: 'Machine Learning', target: 'TensorFlow'},
      {source: 'Machine Learning', target: 'PyTorch'},
    
      // RNN / LSTM / Transformer & Frameworks 相关性
      {source: 'RNN', target: 'PyTorch'},
      {source: 'LSTM', target: 'PyTorch'},
      {source: 'Transformer', target: 'TensorFlow'},
      {source: 'Transformer', target: 'PyTorch'},
    
      // Fuzzing & Machine Learning 相关性
      {source: 'Fuzzing', target: 'TensorFlow'},
      {source: 'Fuzzing', target: 'PyTorch'},
    
      // Conformance Checking & Machine Learning 相关性
      {source: 'Conformance Checking', target: 'Generative Adversarial Networks'},
      {source: 'Conformance Checking', target: 'Graph Neural Networks'},

    // Industry & Other Categories
    {source: 'Network Security', target: 'Cybersecurity'},
  
    // Programming & Other Categories
    {source: 'Programming', target: 'Machine Learning'},
    {source: 'Programming', target: 'Cybersecurity'},
    {source: 'Programming', target: 'Process Mining'},
    {source: 'Programming', target: 'Software Tech'},
  
    // Programming & Frameworks relationships
    {source: 'Python', target: 'TensorFlow'},
    {source: 'Python', target: 'PyTorch'},

    {source: 'Alloy', target: 'Computer Modeling'},
    {source: 'C++', target: 'Computer Modeling'},
    {source: 'Java', target: 'Process Mining'},
    {source: 'Python', target: 'Process Mining'},
    {source: 'Python', target: 'Conformance Checking'},
    {source: 'Java', target: 'Architecture'},
    {source: 'MATLAB', target: 'Computer Modeling'},
    {source: 'Web Application', target: 'V model'},
    {source: 'Web Application', target: 'Project Management'}
  ]
};

// Function to generate a random color, avoiding dark colors
function getRandomColor() {
  const min = 128; // Minimum value for color components to avoid dark colors
  const max = 255; // Maximum value for color components
  const r = Math.floor(Math.random() * (max - min + 1) + min); // Random red value
  const g = Math.floor(Math.random() * (max - min + 1) + min); // Random green value
  const b = Math.floor(Math.random() * (max - min + 1) + min); // Random blue value
  
  // Convert to hexadecimal color code
  return `#${r.toString(16).padStart(2, '0')}${g.toString(16).padStart(2, '0')}${b.toString(16).padStart(2, '0')}`;
}


// Assign random colors to second-level nodes, only if their parent is one of the first-level categories
data.nodes.forEach(d => {
  if (['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.id)) {
    d.r = 200; 
  }
  else if (d.parent && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.parent)) {
    d.color = getRandomColor(); // 给二级节点分配随机颜色
    d.r = 100;  // 设置二级节点的半径为 80
  }
});

data.nodes.forEach(d => {
  let currentParent = d;
  let parentCount = 0;

  // 向上查找父节点的父节点的父节点，直到最多查三层
  while (currentParent && parentCount < 3) {
    currentParent = data.nodes.find(node => node.id === currentParent.parent);
    parentCount++;

    // 只有当查到父节点的父节点的父节点是目标之一时，才改变颜色
    if (parentCount === 3 && currentParent && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(currentParent.id)) {
      // 将当前节点的颜色设置为浅灰色
      d.color = '#D3D3D3';  // 浅灰色
      break;  // 找到后不再继续向上查找
    }
  }
});


  // 创建SVG元素
  const svg = d3.select("#graph");

  // 设置图谱的宽度和高度
  const width = +svg.attr("width");
  const height = +svg.attr("height");

  // 创建缩放行为
  const zoom = d3.zoom()
    .scaleExtent([0.2, 1]) // 设置缩放的范围
    .on("zoom", function(event) {
      svgGroup.attr("transform", event.transform); // 根据缩放和移动来调整图形
    });
    
  svg.call(zoom); // 将缩放行为绑定到SVG

  // 创建一个容器组，用于存放所有图形
  const svgGroup = svg.append("g");

  // 设置力导向图的模拟布局
  const simulation = d3.forceSimulation(data.nodes)
    .force("link", d3.forceLink(data.links).id(d => d.id).distance(150))  // 设置链接的距离
    .force("charge", d3.forceManyBody().strength(-6000))  // 节点之间的排斥力
    .force("center", d3.forceCenter(width / 2, height / 2));  // 设置图谱的中心

    const marker = svg.append("defs").selectAll("marker")
      .data(["arrow"])
      .enter().append("marker")
      .attr("id", "arrow")
      .attr("viewBox", "0 -5 10 10")
      .attr("refX", 37)
      .attr("refY", -1.4)
      .attr("orient", "auto")
      .attr("markerWidth", 6)
      .attr("markerHeight", 6)
      .append("path")
      .attr("d", "M0,-5L10,0L0,5")
      .attr("fill", "#999");
    
    const link = svgGroup.append("g")
      .selectAll(".link")
      .data(data.links)
      .enter().append("path")
      .attr("class", "link")
   .attr("stroke", function(d) {
    // 查找连接线的源节点
    const sourceNode = data.nodes.find(node => node.id === d.source.id);

    // 检查源节点是否是一级节点，如果是，则使用源节点的颜色
    if (sourceNode && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(sourceNode.id)) {
      return sourceNode.color;  // 使用源节点的颜色
    } else {
      return "#999";  // 默认颜色
    }
  })
      .attr("stroke-width", 3)
      .attr("fill", "none")
      .attr("marker-end", "url(#arrow)");

  // 创建图谱的节点
  const node = svgGroup.append("g")
    .selectAll(".node")
    .data(data.nodes)
    .enter().append("circle")
    .attr("class", "node")
    .attr("r", d => d.r || 50)  // 大类节点的半径根据自定义的r值
    .attr("fill", d => d.color || '#FAF0E6')  // 子类继承父类颜色或者使用默认的浅米色
    .call(d3.drag()
      .on("start", dragStart)
      .on("drag", dragging)
      .on("end", dragEnd));

    // 为每个节点添加标签
    svgGroup.append("g")
      .selectAll(".label")
      .data(data.nodes)
      .enter().append("text")
      .attr("class", "label")
      .attr("text-anchor", "middle")  // 文本水平居中
      .style("font-size", d => {
        // 如果 id 为 'Research', 'Industry', 'Programming', 'Software Tech'，则设置字体大小为 50px
        const largeFontIds = ['Research', 'Industry', 'Programming', 'Software Tech'];
        return largeFontIds.includes(d.id) ? "60px" : "30px";  // 其他节点的字号为 30px
      })
      .text(d => d.id);  // 设置文本内容为节点的id


// 监听点击事件
// 创建一个对象来记录每个节点的展开状态
const nodeState = {};

node.on("click", function(event, d) {
  const parentNode = data.nodes.find(node => node.id === d.parent);

  // 只有父节点有颜色且当前节点还没有展开时才执行
  if (parentNode && parentNode.color && !nodeState[d.id]) {
    nodeState[d.id] = true;  // 标记该节点已经展开

    // 展开子节点
    node.each(function(child) {
      if (child.parent === d.id) {
        // 展开子节点
        d3.select(this).style("display", "inline");
        d3.selectAll(".label")
          .filter(label => label.id === child.id)
          .style("display", "inline");

        link.filter(l => l.source.id === child.id || l.target.id === child.id)
          .style("display", "inline");
      }
    });
  }
});



    simulation.on("tick", function() {
      link
        .attr("d", function(d) {
          const dx = d.target.x - d.source.x;
          const dy = d.target.y - d.source.y;
          const dr = Math.sqrt(dx * dx + dy * dy);
          const curve = 0.1;  // Controls the curvature of the links
          return `M${d.source.x},${d.source.y}A${dr},${dr} 0 0,1 ${d.target.x},${d.target.y}`;
        });
    
      node
        .attr("cx", d => d.x)
        .attr("cy", d => d.y);
    
      svgGroup.selectAll(".label")
        .attr("x", d => d.x)
        .attr("y", d => d.y);
    });

  // 拖动事件处理
  function dragStart(event, d) {
    if (!event.active) simulation.alphaTarget(0.3).restart();
    d.fx = d.x;
    d.fy = d.y;
  }

  function dragging(event, d) {
    d.fx = event.x;
    d.fy = event.y;
  }

  function dragEnd(event, d) {
    if (!event.active) simulation.alphaTarget(0);
    d.fx = null;
    d.fy = null;
  }
</script>