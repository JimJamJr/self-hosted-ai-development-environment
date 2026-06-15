# System Overview

The system is divided mainly across 2 machines; a spare PC I have adapted to work as a server, and my main PC. This is mainly due to processing constraints because although not ideal, my PC specs are far better than the server.

## Server

The Server is an old gaming PC I bought from a car boot sale for about £20. It has an old AMD CPU and AMD graphics card. Although I bought it with 8gb of ddr3 ram, the motherboard supports 4 slots so I made use of some additional ddr3 sticks I had to boost the overall ram to 24gb. The server is also connected to wired Ethernet which connects to a switch at my desk for faster communication. After cleaning the PC and adding in the additional ram, I also noticed the fans around the cpu were not ideal so I reorganised them for better airflow and applied new thermal paste.

### Operating System 

Due to the low system specifications of the server I opted for a very light weight Debian 12 install. I also had used this for a previous project so it was somewhat familiar to me. I installed it as a text based OS to further reduce idle processing and did not install anything than the very minimum.

### Security

This is a local system but I wanted to ensure my files are secure since I don't live alone and can't be assured that my network is completely safe. So after some research I decided on tailscale to create a secure local network. I first moved the system over to SSH key authentication so that my pc and server are linked by more than just passwords when I was doing the remote management. Then I downloaded and set up tailscale on the server, and linked it to my PC. Then with tailscale on my PC, laptop, phone and the server, I can now securely access the local network. I also set up the IP for the server to be reserved in my router to ensure the IP remains static and always accessible.

### Server Management

Having completed a small server project in the past I chose to use CasaOS because I am familar with it. Once I had this installed, I had an easy to use UI to continue the rest of the installs of Ollama, and open WebUI. CasaOS also means I can quickly manage the server from any device connected to the local tailscale network as well as monitor the usage as I ran the AI models. 

### AI Infrastructure and Models

The best documented free local host AI I found in my research was Ollama. Because I am new to using AI agents, especially locally, the good documentation was a big benefit to me. Install was made easy by the CasaOS appstore. After install I was also able to remotely install the models using the CasaOS terminal. 

#### llama3.2

As a general assistant model, llama3.2 made sense to put on the server so that I could easily access it often even when I'm not on the main PC. I implemented a low intensity model due to the low specifications of the server, but it works to help with general conversation tasks, documentation, summaries, and research.

#### Qwen 2.5 - Coder

I had decided to install Qwen 2.5 Coder on both my main PC and the server but the server uses a lightweight version. This version is suitable for repetative coding tasks, small functions, and other low intensity tasks. I mainly did this to allow me to have a spare code agent to spread some of the load off of my main PC but also to make it available to use when I am not on my main PC. Its training on Python, HTML/CSS, and JS made it ideal for this.

#### Open WebUI

In order to have an easy place to store chats and use llama3.2 outside of VS code, I decided to install Open WebUI on the server. This again was made easy by the CasaOS appstore. Once installed I set it up so that I can access it anywhere on the local using the IP from tailscale so that it is continued to be secured. This then provides me with an easy to use interface for conversations about projects on dedicated chats with memory.

## Main PC

My main PC is where I do most of my work when I am home and on my local network. It also has a much newer AMD CPU, 64gb ddr4 ram, a 2tb m.2, but does have a slightly older GPU. Because of this I decided to put the more intensive models on my PC. 

### Ollama Models

#### Qwen 2.5 - Coder : 14b

I chose to use qwen coder again on my main PC as I did on the server so that the code would be consistent. However I installed the 14b model so that when I have a more powerful model for larger programming tasks on my PC. The other benefit is that the implementation with Roo Code for VS code would be much stronger. And the most important benefit being that it can quickly access all the files it needs free of charge and help with development to high degrees of accuracy.

#### Qwen 3 : 14b

In order to achieve robust, scalable systems, I opted to install the Qwen 3 model so that I would have a good model to help with planning. This way I can more easily design systems for implementation. Qwen 3 is better at reasoning and planning than Qwen 2.5 but still has good coding awareness so it is good for providing architecture insights and suggestions. I hope this will streamline my design processes while also improving the quality of my systems and making them more easily scalable.

#### DeepSeek R1 : 14b

The last model I installed on my main PC was DeepSeek R1 14b because its problem solving and logical analysis make it optimal for reviewing code and pointing out pitfalls. The idea beign that when I have completed a module, I can use this model to review and improve it so that the final code is higher quality. This should also help with difficult errors by locating them quicker and finding solutions faster too.

### Roo Code

To use all the AI models on my PC, I instsalled the Roo code plugin for VS Code. This makes it easy to manage them all right where my code is. By using the server IP port for ollama from tailscale, I was quickly able to link both the local and server models to different setups. From there I configured a number of different agents for all their intended purposes so they are ready to use when I need them.
