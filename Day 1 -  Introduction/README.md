# Day 1: Introduction to Ansible

---

- Why Ansible
    
    ![image.png](Day%201%20Introduction%20to%20Ansible%20c581d5d7bc234a70ae04f0683fcd828a/image.png)
    
    ![image.png](Day%201%20Introduction%20to%20Ansible%20c581d5d7bc234a70ae04f0683fcd828a/image%201.png)
    
    ![image.png](Day%201%20Introduction%20to%20Ansible%20c581d5d7bc234a70ae04f0683fcd828a/image%202.png)
    

- Why ansible, if puppet, chef and salt like told were already their,what are their disadvantages and how ansible overcome their disadvantages
    
    Ansible gained popularity over other configuration management tools like Puppet, Chef, and Salt due to its simplicity, ease of use, and powerful features. Here's a detailed breakdown of why Ansible stands out and how it overcomes some of the limitations of those tools:
    
    - 1. **Agentless vs. Agent-based Architecture**:
        - **Puppet, Chef, Salt**: These tools generally use an **agent-based** architecture, meaning each managed node requires an agent or client installed and running on the system. This adds complexity to setup and maintenance, especially in large-scale environments.
        - **Ansible**: It is **agentless**, meaning no software needs to be installed on the managed nodes. Ansible uses SSH (or WinRM for Windows) to communicate with nodes, which is far simpler and reduces overhead.
        
        **Advantage**:
        
        - **Ease of setup**: No agents to install or manage.
        - **Reduced overhead**: Fewer processes and services running on nodes, leading to improved performance and reduced maintenance.
    - 2. **Learning Curve and Simplicity**:
        - **Puppet and Chef**: Both tools require the use of specialized languages—**Puppet** uses **Puppet DSL** and **Chef** uses **Ruby**. This adds a steep learning curve for those unfamiliar with these languages.
        
        - **Ansible**: Uses simple **YAML** files for writing playbooks, which are easy to read and write. YAML is a human-readable format that requires no additional coding skills beyond basic logic.
        
        **Advantage**:
        
        - **Low learning curve**: Easier for beginners and non-programmers to pick up quickly.
        - **Readability**: YAML is intuitive and easily understandable by teams across different skill levels.
    - 3. **Push vs. Pull Configuration**:
        - **Puppet and Chef**: These tools generally work on a **pull-based** model, where agents on the managed nodes pull configurations from the central server at defined intervals. This can sometimes lead to delays and inconsistency, especially in dynamic environments.
        - **Ansible**: Operates in a **push-based** model, where the control node (the machine running Ansible) pushes configurations to the managed nodes instantly. This ensures immediate execution of tasks, providing faster and more deterministic results.
        
        **Advantage**:
        
        - **Real-time execution**: Push-based model allows for immediate changes without waiting for the node to "pull" the configuration.
        - **Better control**: Administrators can control exactly when and where configurations are applied.
    - 4. **Scalability and Performance**:
        - **SaltStack**: Salt uses a **message bus** and is faster than Puppet and Chef in many cases. However, SaltStack’s architecture can become complex when scaling due to the need for multiple daemons (Master, Minion) and configuration synchronization.
        - **Puppet and Chef**: They also face challenges in scaling, particularly because of their agent-based model and centralized management, which can lead to performance bottlenecks.
        - **Ansible**: Being agentless, Ansible scales more efficiently because there are no additional services or daemons running on the managed nodes. The push model combined with SSH makes it relatively simple to manage thousands of nodes.
        
        **Advantage**:
        
        - **Scalability**: Easier to scale with fewer moving parts (no agents, daemons).
        - **Fewer bottlenecks**: The decentralized nature of Ansible ensures faster execution without centralized dependency.
    - 5. **Dependencies and Ecosystem**:
        - **Puppet and Chef**: Both have a large ecosystem with robust modules and cookbooks but may require several dependencies or external components to work efficiently.
        - **Ansible**: Comes with minimal dependencies—just **Python** (which is almost always available on Linux distributions by default). It has a large, growing ecosystem of pre-built roles available via **Ansible Galaxy**.
        
        **Advantage**:
        
        - **Minimal dependencies**: Only SSH and Python (for Linux) or WinRM (for Windows) are needed to get started.
        - **Simple ecosystem**: Easier to integrate with other tools like Jenkins, GitLab, and CI/CD pipelines.
    - 6. **Declarative vs. Procedural**:
        - **Puppet and Chef**: These tools are **declarative**, meaning you define the end state of the system, and the tool figures out how to achieve it. This is generally good for ensuring consistency, but it can sometimes lead to confusion if the state management isn't clearly defined.
        - **Ansible**: Can be both **declarative** and **procedural**. While you define what you want, you can also control how tasks are executed, giving you more flexibility in certain automation tasks.
        
        **Advantage**:
        
        - **Flexibility**: Provides both declarative and procedural approaches to task execution.
    - 7. **Extensibility and Customization**:
        - **Puppet and Chef**: Offer rich customization options but may require more advanced knowledge of their respective languages (Puppet DSL or Ruby) to extend or customize.
        - **Ansible**: Is highly extensible, and since it uses Python under the hood, extending Ansible is straightforward for Python developers. Moreover, playbooks and roles can be easily customized using Ansible's extensive module library.
        
        **Advantage**:
        
        - **Easier to extend**: Python-based extensions and a large community-supported module repository (Ansible Galaxy).
    - Conclusion: Why Ansible?
        
        Ansible excels in environments where simplicity, speed, and ease of use are priorities. It offers:
        
        - **No agents** (unlike Puppet, Chef, Salt), making it easier to maintain.
        - **YAML-based playbooks** (simpler than Puppet’s DSL or Chef’s Ruby).
        - **Push-based architecture** (offers more control and faster execution).
        - **Minimal dependencies** (just SSH and Python).
        - **Easier to learn and adopt** due to its human-readable syntax.
        
        For organizations that want a lightweight, powerful, and flexible automation tool without the steep learning curve or the complexity of managing agents, Ansible is often the preferred choice.
        
- Conclusion
    
    Here are concise, interview-focused points highlighting why Ansible is preferred over Puppet, Chef, and Salt:
    
    ### 1. **Agentless Architecture**:
    
    - **Ansible**: No agents required; uses SSH (or WinRM for Windows).
    - **Puppet/Chef/Salt**: Requires agents on managed nodes, increasing setup and maintenance complexity.
    
    ### 2. **Ease of Use (YAML vs DSL)**:
    
    - **Ansible**: Uses **YAML** for playbooks (simple, human-readable).
    - **Puppet/Chef**: Use specific languages (Puppet DSL, Ruby for Chef), increasing learning curve.
    
    ### 3. **Push-based vs. Pull-based**:
    
    - **Ansible**: **Push-based** model; configurations are applied in real-time.
    - **Puppet/Chef**: **Pull-based** model; agents pull updates, causing potential delays.
    
    ### 4. **Minimal Dependencies**:
    
    - **Ansible**: Only requires **SSH** and **Python** on nodes (default on most systems).
    - **Puppet/Chef**: Requires additional packages and services.
    
    ### 5. **Scalability and Performance**:
    
    - **Ansible**: Scales easily with no agents or daemons; suitable for large environments.
    - **Puppet/Chef**: Scaling can lead to performance bottlenecks due to agent dependencies.
    
    ### 6. **Declarative and Procedural Flexibility**:
    
    - **Ansible**: Supports both **declarative** and **procedural** approaches.
    - **Puppet/Chef**: Primarily **declarative**, less flexible in defining task execution steps.
    
    ### 7. **Ecosystem and Extensibility**:
    
    - **Ansible**: Rich ecosystem with **Ansible Galaxy**; easily extendable via Python.
    - **Puppet/Chef**: Require more advanced knowledge to customize (Puppet DSL/Ruby).
    
    ### 8. **Learning Curve**:
    
    - **Ansible**: Lower learning curve; easy to adopt for both developers and sysadmins.
    - **Puppet/Chef**: Higher learning curve due to language and agent setup.
    
    These points highlight Ansible's advantages for ease of use, speed, scalability, and flexibility during an interview.
    

---

- **What is Ansible ?**
    - 
        
        ![image.png](Day%201%20Introduction%20to%20Ansible%20c581d5d7bc234a70ae04f0683fcd828a/image%203.png)
        
        ![image.png](Day%201%20Introduction%20to%20Ansible%20c581d5d7bc234a70ae04f0683fcd828a/image%204.png)
        
        ![image.png](Day%201%20Introduction%20to%20Ansible%20c581d5d7bc234a70ae04f0683fcd828a/image%205.png)
        
    
    Ansible is an open source IT automation engine that automates
    
    - provisioning
    - configuration management
    - application deployment
    - orchestration
    
    and many other IT processes. It is free to use, and the project benefits from the experience and intelligence of its thousands of contributors.
    
    ---
    
- **How Ansible works ?**
    
    Ansible is agentless in nature, which means you don't need install any software on the manage nodes.
    
    For automating Linux and Windows, Ansible connects to managed nodes and pushes out small programs—called Ansible modules—to them. These programs are written to be resource models of the desired state of the system. Ansible then executes these modules (over SSH by default), and removes them when finished. These modules are designed to be idempotent when possible, so that they only make changes to a system when necessary.
    
    For automating network devices and other IT appliances where modules cannot be executed, Ansible runs on the control node. Since Ansible is agentless, it can still communicate with devices without requiring an application or service to be installed on the managed node.
    

---