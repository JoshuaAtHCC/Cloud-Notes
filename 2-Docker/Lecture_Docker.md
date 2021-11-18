# Docker Lecture: https://www.youtube.com/watch?v=e_YEMorNAQc&list=PLzOJMOiC_x7e2gt9Fn1S0aqMfLXr1n3Hw
**What is Docker?**
Docker is a tool that makes development **efficient** and **predictable**

**What is a Container?**
A standard unit of software that packages up code an all its dependencies so the application runs quickly and reliably from one computing environment to another.
Features:
- Lightweight
- Standalone
- Includes everything you need to run an application: code, runtime, system tools, system libraries, and settings 

**Containers vs. Virtual Machines**
![](https://i.imgur.com/HDDmFsd.png)
Containers compared to VMs:
- Take up less space (10 MB vs 10 GB)
- Are more versatile (Can handle more applications and require fewer VMs and Operating Systems)
- Faster to boot

---

### Anatomy of a Dockerfile
**Dockerfile**: A file used to specify how to build a docker image 
```
FROM parentimage:latest  
#this is a comment  
ENV “environmentVariableKey”=“environmentVariableValue”  
RUN commandToRunInShell  
RUN ["executable", "param1", "param2"]  
COPY ./localsourceFolder /DestFolderWithinImage  
WORKDIR /DestFolderWithinImage  
EXPOSE 80/tcp  
#above line exposes port 80 to the docker virtual network  
CMD ["executable","param1","param2"]  
#above line is the one command to run in the container  
#alternative method specifies executable in ENTRYPOINT and calls CMD with only params
```
More information: https://www.freecodecamp.org/news/the-docker-handbook/#how-to-write-the-development-dockerfile

---

![](https://i.imgur.com/clcDEvg.png)
Docker Cheat Sheet: https://www.docker.com/sites/default/files/d8/2019-09/docker-cheat-sheet.pdf

---

