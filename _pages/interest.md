---
layout: page
title: Interest
permalink: /interest/
nav: true
nav_order: 5
---

Here is my interest network. <strong>Zoom-in</strong> to explore it!

<svg id="graph" width="1000" height="800"></svg>

<script src="https://d3js.org/d3.v7.min.js"></script>

<!--
INSTRUCTIONS:
- To add a new interest, simply edit _data/interests.yml and add your node in the correct place.
- The visualization will update automatically based on the YAML structure.
- The YAML data is injected into this page using Jekyll/Liquid.
-->

<script>
// interests data injected by Jekyll/Liquid
const interests = {{ site.data.interests | jsonify }};

// Helper function: recursively traverse YAML tree to build nodes and links
function traverse(node, parent = null, nodes = [], links = []) {
  const {id, color, children} = node;
  const nodeObj = {id, group: id, color, parent: parent ? parent.id : undefined};
  nodes.push(nodeObj);
  if (parent) {
    links.push({source: parent.id, target: id});
  }
  if (children) {
    children.forEach(child => traverse(child, nodeObj, nodes, links));
  }
  return {nodes, links};
}

let nodes = [], links = [];
interests.forEach(root => {
  const result = traverse(root);
  nodes = nodes.concat(result.nodes);
  links = links.concat(result.links);
});

// Add cross-domain connections based on knowledge
const crossDomainLinks = [
  // Programming -> Research connections
  {source: 'Python', target: 'Process Mining'},
  {source: 'Python', target: 'Machine Learning'},
  {source: 'Python', target: 'Computer Modeling'},
  {source: 'Python', target: 'Conformance Checking'},
  {source: 'Java', target: 'Process Mining'},
  {source: 'Java', target: 'Architecture'},
  {source: 'C++', target: 'Computer Modeling'},
  {source: 'MATLAB', target: 'Computer Modeling'},
  {source: 'Alloy', target: 'Computer Modeling'},
  {source: 'Ada', target: 'Cybersecurity'},
  {source: 'Javascript', target: 'Web Application'},
  {source: 'HTML', target: 'Web Application'},
  {source: 'Typescript', target: 'Web Application'},
  {source: 'PHP', target: 'Project Management'},
  
  // Programming -> Software Tech connections
  {source: 'Python', target: 'TensorFlow'},
  {source: 'Python', target: 'PyTorch'},
  {source: 'Java', target: 'Servlet'},
  {source: 'Javascript', target: 'React'},
  {source: 'Javascript', target: 'Vue'},
  {source: 'Typescript', target: 'React'},
  {source: 'HTML', target: 'React'},
  {source: 'HTML', target: 'Vue'},
  
  // Research -> Software Tech connections
  {source: 'Machine Learning', target: 'TensorFlow'},
  {source: 'Machine Learning', target: 'PyTorch'},
  {source: 'Time Series Analysis', target: 'TensorFlow'},
  {source: 'Time Series Analysis', target: 'PyTorch'},
  {source: 'RNN', target: 'PyTorch'},
  {source: 'LSTM', target: 'PyTorch'},
  {source: 'Transformer', target: 'TensorFlow'},
  {source: 'Transformer', target: 'PyTorch'},
  {source: 'Mamba', target: 'PyTorch'},
  {source: 'Generative Adversarial Networks', target: 'TensorFlow'},
  {source: 'Graph Neural Networks', target: 'PyTorch'},
  {source: 'Clustering', target: 'Process Discovery'},
  {source: 'Clustering', target: 'Conformance Checking'},
  {source: 'RNN', target: 'RNN-based Approximation'},
  {source: 'Mamba', target: 'RNN-based Approximation'},
  {source: 'Graph Neural Networks', target: 'Anomaly Detection'},
  {source: 'Conformance Checking', target: 'Generative Adversarial Networks'},
  {source: 'Conformance Checking', target: 'Graph Neural Networks'},
  
  // Industry connections
  {source: 'Network Security', target: 'Cybersecurity'},
  {source: 'Web Application', target: 'V model'},
  {source: 'Web Application', target: 'Project Management'},
  {source: 'Maven', target: 'Java'},
  
  // Software Tech -> Research connections
  {source: 'Fuzzing', target: 'TensorFlow'},
  {source: 'Fuzzing', target: 'PyTorch'},
  {source: 'Testing', target: 'V model'},
  {source: 'Framework', target: 'Django'},
  {source: 'Framework', target: 'Servlet'},
  {source: 'Framework', target: 'Next.js'},
  {source: 'Framework', target: 'TensorFlow'},
  {source: 'Framework', target: 'PyTorch'},
  
  // Additional cross-domain connections
  {source: 'Programming', target: 'Machine Learning'},
  {source: 'Programming', target: 'Cybersecurity'},
  {source: 'Programming', target: 'Process Mining'},
  {source: 'Programming', target: 'Software Tech'},
  {source: 'Industry', target: 'Project Management'},
  {source: 'Research', target: 'AI in Education'},
  {source: 'Logic Education', target: 'AI in Education'},
  {source: 'Process Mining', target: 'Process Mining in Education'},
  {source: 'Fuzzy Miner', target: 'Process Mining in Education'},
  {source: 'Stochastic Process Miner', target: 'Process Mining in Education'},
  {source: 'AI in Education', target: 'Self-Regulated Learning (SRL)'},
  {source: 'AI in Education', target: 'Chatbot-based Learning'},
  {source: 'AI in Education', target: 'GenAI-powered Scaffolding'},
  {source: 'AI in Education', target: 'Process Mining in Education'},
  {source: 'Conformance Checking', target: 'Sampling Approximation'},
  {source: 'Conformance Checking', target: 'RNN-based Approximation'},
  {source: 'Conformance Checking', target: 'Stochastic Conformance Checking'},
  {source: 'Testing', target: 'Fuzzing'},
  {source: 'Fuzzing', target: 'AFLNet'},
  {source: 'Fuzzing', target: 'LibFuzzer'},
  {source: 'Framework', target: 'React'},
  {source: 'Framework', target: 'Vue'},
  {source: 'Framework', target: 'Django'},
  {source: 'Framework', target: 'Servlet'},
  {source: 'Framework', target: 'Next.js'},
  {source: 'Framework', target: 'TensorFlow'},
  {source: 'Framework', target: 'PyTorch'},
  {source: 'Machine Learning', target: 'Generative Adversarial Networks'},
  {source: 'Machine Learning', target: 'Graph Neural Networks'},
  {source: 'Machine Learning', target: 'Time Series Analysis'},
  {source: 'Machine Learning', target: 'Clustering'},
  {source: 'Time Series Analysis', target: 'RNN'},
  {source: 'Time Series Analysis', target: 'LSTM'},
  {source: 'Time Series Analysis', target: 'Transformer'},
  {source: 'Time Series Analysis', target: 'Mamba'},
  {source: 'Process Mining', target: 'Process Discovery'},
  {source: 'Process Mining', target: 'Process Prediction'},
  {source: 'Process Mining', target: 'Conformance Checking'},
  {source: 'Process Mining', target: 'Anomaly Detection'},
  {source: 'Process Discovery', target: 'Fuzzy Miner'},
  {source: 'Process Discovery', target: 'Heuristic Miner'},
  {source: 'Process Discovery', target: 'Stochastic Process Miner'},
      {source: 'Research', target: 'Process Mining'},
      {source: 'Research', target: 'Cybersecurity'},
      {source: 'Research', target: 'Computer Modeling'},
      {source: 'Research', target: 'Machine Learning'},
  {source: 'Research', target: 'Knowledge Representation and Reasoning'},
  {source: 'Research', target: 'Logic Education'},
      {source: 'Research', target: 'AI in Education'},
      {source: 'Industry', target: 'Network Security'},
      {source: 'Industry', target: 'Web Application'},
      {source: 'Industry', target: 'Project Management'},
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
  {source: 'Software Tech', target: 'Framework'}
];

// Combine original links with cross-domain links
const allLinks = links.concat(crossDomainLinks);

renderGraph({nodes, links: allLinks});

function renderGraph(data) {
  // 创建SVG元素
  const svg = d3.select("#graph");
  // 设置图谱的宽度和高度
  const width = +svg.attr("width");
  const height = +svg.attr("height");

  // 设置SVG的transform scale固定为1.0
  svg.style("transform", "scale(1.0)");
  svg.style("transform-origin", "top left");
  // 创建缩放行为
  const zoom = d3.zoom()
    .scaleExtent([0.2, 3])
    .on("zoom", function(event) {
      svgGroup.attr("transform", event.transform);
    });
  svg.call(zoom);
  // 创建一个容器组，用于存放所有图形
  const svgGroup = svg.append("g");
  // 设置力导向图的模拟布局
  const simulation = d3.forceSimulation(data.nodes)
    .force("link", d3.forceLink(data.links).id(d => d.id).distance(80))  // 减少链接距离，让节点更紧凑
    .force("charge", d3.forceManyBody().strength(-8000))  // 增加排斥力，让节点分布更均匀
    .force("center", d3.forceCenter(width / 2, height / 2))
    .force("collision", d3.forceCollide().radius(d => {
      // 为一级节点设置碰撞半径，让它们更紧凑
      if (['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.id)) {
        return 250;  // 一级节点碰撞半径
      } else if (d.parent && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.parent)) {
        return 150;  // 二级节点碰撞半径
      } else {
        return 80;   // 其他节点碰撞半径
      }
    }));
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
    const sourceNode = data.nodes.find(node => node.id === d.source.id);
    if (sourceNode && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(sourceNode.id)) {
        return sourceNode.color;
    } else {
        return "#999";
    }
  })
      .attr("stroke-width", 3)
      .attr("fill", "none")
      .attr("marker-end", "url(#arrow)");
  const node = svgGroup.append("g")
    .selectAll(".node")
    .data(data.nodes)
    .enter().append("circle")
    .attr("class", "node")
    .attr("r", d => {
      // 根据层级设置节点大小
      if (['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.id)) {
        return 200;  // 一级节点最大
      } else if (d.parent && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.parent)) {
        return 120;  // 二级节点中等
      } else {
        return 50;   // 三级及以下节点最小（保持现在大小）
      }
    })
    .attr("fill", d => {
      // 为节点分配颜色，确保一级和二级节点颜色不重复
      if (d.color) {
        return d.color;  // 一级节点保持原有颜色
      } else if (d.parent && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.parent)) {
        // 为二级节点分配不重复的颜色
        const colors = ['#FF6B6B', '#4ECDC4', '#45B7D1', '#96CEB4', '#FFEAA7', '#DDA0DD', '#98D8C8', '#F7DC6F', '#BB8FCE', '#85C1E9', '#F39C12', '#E74C3C', '#9B59B6', '#3498DB', '#1ABC9C'];
        const index = d.id.charCodeAt(0) % colors.length;
        return colors[index];
      } else {
        return '#FAF0E6';  // 其他节点默认颜色
      }
    })
    .attr("stroke", d => {
      // 为一级节点添加特效边框
      if (['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.id)) {
        return '#333';
      }
      return 'none';
    })
    .attr("stroke-width", d => {
      // 为一级节点添加粗边框
      if (['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.id)) {
        return 3;
      }
      return 0;
    })
    .style("filter", d => {
      // 为一级节点添加阴影特效
      if (['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.id)) {
        return 'drop-shadow(0 4px 8px rgba(0,0,0,0.3))';
      }
      return 'none';
    })
    .call(d3.drag()
      .on("start", dragStart)
      .on("drag", dragging)
      .on("end", dragEnd));
    svgGroup.append("g")
      .selectAll(".label")
      .data(data.nodes)
      .enter().append("text")
      .attr("class", "label")
    .attr("text-anchor", "middle")
      .style("font-size", d => {
      // 根据层级设置字体大小
      if (['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.id)) {
        return "60px";  // 一级节点字体最大
      } else if (d.parent && ['Research', 'Industry', 'Programming', 'Software Tech'].includes(d.parent)) {
        return "40px";  // 二级节点字体中等
      } else {
        return "30px";  // 三级及以下节点字体最小（保持现在大小）
      }
    })
    .text(d => d.id);
// 监听点击事件
const nodeState = {};
node.on("click", function(event, d) {
  const parentNode = data.nodes.find(node => node.id === d.parent);
  if (parentNode && parentNode.color && !nodeState[d.id]) {
      nodeState[d.id] = true;
    node.each(function(child) {
      if (child.parent === d.id) {
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
        const curve = 0.1;
          return `M${d.source.x},${d.source.y}A${dr},${dr} 0 0,1 ${d.target.x},${d.target.y}`;
        });
      node
        .attr("cx", d => d.x)
        .attr("cy", d => d.y);
      svgGroup.selectAll(".label")
        .attr("x", d => d.x)
        .attr("y", d => d.y);
    });
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
}



  // 设置默认zoom更小
  svg.call(zoom.transform, d3.zoomIdentity.scale(0.6));
</script>