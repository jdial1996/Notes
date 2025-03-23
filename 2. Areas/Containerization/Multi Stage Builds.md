- **Always default to using multi-stage builds**, regardless of whether the application is written in a compiled or interpreted language, as it consistently helps reduce the attack surface and produce cleaner, more secure container images.


**Compiled Multi Stage**
- The first stage should include all dependencies required to compile the program and output an executable
- The second stage should include executable produced by the first stage  and any required runtime dependencies
- This results in a smaller and secure image. 


**Interpreted Multi Stage**
- The first stage should install all necessary application  dependencies and perform any setup tasks (eg. installing packages with pip)
- The **second stage** should include only the **application code** and the **installed dependencies** needed to **run the app**, excluding build tools or dev artifacts.


**Bonus**
- Compiled containers can use minimal scratch containers since they don't need anything else to run. 
- Interpreted containers need a base image with the interpreter pre installed 