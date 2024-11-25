<img src="https://documentation.wazuh.com/current/_images/access-wazuh-server-api1.png" alt="YEN Project Banner">

</head>
<body>
    <h1>YEN: Real-Time Security Monitoring and Analysis</h1>
    <p><strong>YEN</strong> is an advanced real-time security solution that integrates <strong>Wazuh</strong>, <strong>ELK Stack</strong>, and <strong>Sysmon</strong> to provide unparalleled monitoring, analysis, and threat detection capabilities. Designed for modern security operations, it delivers actionable insights with real-time alerts and dynamic visualization.</p>
    
<h2>🔍 Project Highlights</h2>
    <div class="highlight">
        <ul>
            <li>Centralized log collection and normalization.</li>
            <li>Advanced threat detection with customizable rules.</li>
            <li>High-performance visualization and analytics via Kibana.</li>
            <li>Seamless integration of Wazuh, ELK Stack, and Sysmon.</li>
        </ul>
    </div>
    
<h2>⚙️ Architecture Overview</h2>
    <p>The following components form the backbone of <strong>YEN</strong>:</p>
    <h3>1. Wazuh</h3>
    <ul>
        <li><strong>Functionality:</strong> Host-based Intrusion Detection System (HIDS).</li>
        <li><strong>Features:</strong> Threat detection, log collection, policy monitoring, and alerting.</li>
    </ul>
    <h3>2. ELK Stack</h3>
    <ul>
        <li><strong>Elasticsearch:</strong> Indexes and stores log data for rapid querying.</li>
        <li><strong>Logstash:</strong> Processes and routes logs to Elasticsearch.</li>
        <li><strong>Kibana:</strong> Offers rich, interactive dashboards and visualizations.</li>
    </ul>
    <h3>3. Sysmon</h3>
    <ul>
        <li><strong>Functionality:</strong> High-detail event monitoring for Windows systems.</li>
        <li><strong>Key Features:</strong> Process tracking, file monitoring, and network connection logging.</li>
    </ul>
    
   <h2>🛠️ Installation and Configuration</h2>
    <h3>Docker-Based Installation</h3>
    <p>This guide assumes you have Docker and Docker Compose installed on your system. If not, install them from the <a href="https://docs.docker.com/get-docker/" target="_blank">Docker website</a>.</p>
    
<h4>Step 1: Wazuh Installation</h4>
    <p>Clone the Wazuh Docker repository and navigate to the directory:</p>
    <pre><code>git clone https://github.com/wazuh/wazuh-docker.git</code></pre>
    <pre><code>cd wazuh-docker</code></pre>
    <p>Edit the <code>docker-compose.yml</code> file to customize the setup and then run:</p>
    <pre><code>docker-compose up -d</code></pre>
    <p>Access the Wazuh dashboard at <a href="http://localhost:5601" target="_blank">http://localhost:5601</a> (default credentials: admin/admin).</p>
    
<h4>Step 2: ELK Stack Installation</h4>
    <h5>Elasticsearch</h5>
    <p>Follow the official guide for running Elasticsearch using Docker: <a href="https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html" target="_blank">Elasticsearch Docker Guide</a>.</p>
    <p>Basic command to start Elasticsearch:</p>
    <pre><code>docker run -d --name elasticsearch \
        -p 9200:9200 -p 9300:9300 \
        -e "discovery.type=single-node" \
        docker.elastic.co/elasticsearch/elasticsearch:8.10.1</code></pre>
    
<h5>Logstash</h5>
    <p>Refer to the Logstash Docker guide for installation: <a href="https://www.elastic.co/guide/en/logstash/current/docker.html" target="_blank">Logstash Docker Guide</a>.</p>
    <p>Run the following command to start Logstash:</p>
    <pre><code>docker run -d --name logstash \
        -p 5044:5044 -p 9600:9600 \
        docker.elastic.co/logstash/logstash:8.10.1</code></pre>
    
 <h5>Kibana</h5>
    <p>Refer to the Kibana Docker guide: <a href="https://www.elastic.co/guide/en/kibana/current/docker.html" target="_blank">Kibana Docker Guide</a>.</p>
    <p>Run Kibana with the following command:</p>
    <pre><code>docker run -d --name kibana \
        -p 5601:5601 \
        docker.elastic.co/kibana/kibana:8.10.1</code></pre>
    <p>Access Kibana at <a href="http://localhost:5601" target="_blank">http://localhost:5601</a>.</p>
    
<h4>Step 3: Integration</h4>
    <p>Ensure Wazuh outputs are routed through Logstash into Elasticsearch for storage and analysis. Customize Logstash configurations as needed for proper log parsing.</p>
    
 <h2>📊 Use Cases</h2>
    <ul>
        <li><strong>Proactive Threat Hunting:</strong> Discover and mitigate potential threats before they escalate.</li>
        <li><strong>Incident Response:</strong> Real-time alerts facilitate quick action against security incidents.</li>
        <li><strong>Regulatory Compliance:</strong> Maintain detailed records for audits and compliance mandates.</li>
    </ul>
    
 <h2>🤝 Contributing</h2>
    <p>We welcome contributions! Feel free to submit issues or pull requests to enhance <strong>YEN</strong>.</p>
    
<h2>📞 Support</h2>
    <p>For questions or assistance, reach out to us at <a href="mailto:4bhijith@proton.me">Admin</a>.</p>
    

   <footer>
        <p><strong>YEN:</strong> Strengthening cybersecurity with real-time precision.</p>
    </footer>
</body>
</html>
