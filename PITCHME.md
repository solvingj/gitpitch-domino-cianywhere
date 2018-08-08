## Domino and CI Anywhere
*CI Tools For Build Orchestration*

---
### Me 
* Github/Twitter : @solvingj
* Email:  jerrywiltse@gmail.com

---

## Bincrafters
*Open-Source Devops Team* 

![Image](./assets/md/assets/BcCube128.png)

---
### Find Us Online

* https://opencollective.com/bincrafters
* https://bincrafters.github.io
* https://twitter.com/bincrafters
* https://github.com/bincrafters
* https://www.youtube.com/watch?v=v2QiNTvco5E
---
### Projects on Github

![Image](./assets/md/assets/BcGithub.png)

---
### Packages on Bintray

![Image](./assets/md/assets/BcBintray.png)

---
### CI Anywhere - CI Abstraction Layer
- Generalize common CI features
- Decouple selected logic from CI implementation
- Python script framework

---
### CI Anywhere - Prior Art
- github.com/solvingj/go-github-release-test
- Conan Package Tools
	- Run python build.py anywhere,  CI or Local
	- Incubating and Evolving for 2+ years
	- Features for both enterprise and OSS CI's
	- Primitive yet brilliant and invaluable
	
---
### CI Anywhere - Motivation
- Any non-trivial scripting with YML is aweful
- OS-Specific scripting languages have issues
- CI's have 90% similar features
- Reproducing a CI job locally is invaluable 
- .... and usually impossible
- Lots of redundant hand-rolled cleanup logic
- Scripts typically lack unit testing

---
### CI Anywhere - Motivation
- Choosing and configuring a new CI is painful
- Each CI's is good at some things, bad at others
- Most struggle to support new technology quickly
- Proprietary plugins needed for basic things
- Adding/changing CI becoming more common

---
### CI Anywhere - Conan Package Tools
- https://github.com/conan-io/conan-package-tools
- Major part of inspiration
- Perfect example of a generalized implementation
- Standardizes universal boilerplate tasks
---
### CI Anywhere - Conan Package Tools
- Example boilerplate tasks - Build with Docker:
	- Optionally update container with pull 
	- Optionally update code in container before run
	- Mounting current working directory
	- sudo both inside and outside docker commands
	- Docker entry script lets user do anything pre-build

---
### CI Anywhere - Conan Package Tools
- Itelligently layers defaults, env vars, script params
- Artifact publishing and credential pre-verification
- Git branch detection and commit parsing
- Shows importance of language-specific features

---
### CI Anywhere - Conan Package Tools
- More accessible extensibility model (code sharing)
- Simply create and share python modules via PIP
- Bincrafters package tools good example
- Compare with creating a custom plugin for CI XYZ
- Jenkins just added "Shared Libraries" feature

---
### Travis CI example
```yml
before_install: python ci/travis_pipeline.py -step_name before_install
install: python ci/travis_pipeline.py -step_name install
script: python ci/travis_pipeline.py -step_name script
after_success: python ci/travis_pipeline.py -step_name after_success
```

---
### Appveyor example
```yml
install: python ci/appveyor_pipeline.py -step_name install
build_script: python ci/appveyor_pipeline.py -step_name build_script
after_build: python ci/appveyor_pipeline.py -step_name after_build
deploy_script: python ci/appveyor_pipeline.py -step_name deploy_script
```

---
### CI Anywhere - Features
- Commit parsing = CI Command/Control
- "Publish" helpers for all package types
- Generic Credential Management
- Generic Environment Variable Definitions

---

## Project Domino
*A CI-agnostic Project-Level Dependency System*

---
### Abstract CI Dependencies
* Github is a DAG
* Your Enterprise Codebase is a DAG
* Upstream project build trigger downstream CI 
* Like Libraries.io - but trigger jobs instead of email

---
### Prior Art
* Libraries.io - Simple, good indicator of demand
* Numerous other recent competitors to Libraries.io
* Fedora - https://release-monitoring.org/projects
* Modern CI Systems trigger from "upstream builds"
* All proprietary implementations of a simple concept

---
### Domino Motivation
* C/C++ has unique property of ABI compatibility 
* Even if API changes, downstream might break
* Bincrafters : 200+ Packages : Interdependent
* Realized our needs are universalish among PM's
	* Apt/Yum/Brew/Conda/Vcpkg/Choco/Onepkg/etc
* Realized it's needed in enterprise as much as OSS
* Great candidate to generalize and open-source

---
### Domino Use-Cases
* Downstream dependency libraries
* Downstream package manager repos
* Flexible build policies for downstream consumers 
* A CI agnostic dependency definition layer
* For Enterprise
	* Build based on OSS and internal deps
* For OSS
	* Single source of truth for multiple CI:
		* Travis/Appveyor/CircleCI/Etc

---
### Takeaways
* Bincrafters Looking for New Members + Sponsors
* ... especially if you have C/C++ code
* Also looking for ideas and feedback
* Reach out to me to get involved
	
---
### Thank You
* Github/Twitter : @solvingj
* Email:  jerrywiltse@gmail.com