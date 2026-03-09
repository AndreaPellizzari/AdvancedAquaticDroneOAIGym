<a id="readme-top"></a>
[![Contributors][contributors-shield]][contributors-url]
[![Issues][issues-shield]][issues-url]
[![Unlicense License][license-shield]][license-url]
![java-shield]

<!-- [Funzioni da implementare](https://gist.github.com/AndreaPellizzari/7df0bee0c5017cf846bf2cb3f5d8702c) -->
<br />
<div align="center">
  <h1 align="center">Advanced acquatic drone OAI Gym env project</h1>

  <p align="center">
    Progetto di esame per corso accademico in intelligenza artificiale basato sull'ambiente OpenAI "Advanced aquatic drone".
    <br />
    <i>Examination project for academic course in artificial intelligence based on the "Advanced aquatic drone" OpenAI environment.</i>
    <br />
    <br />
    <a href="https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym/tree/main/doc"><strong>Explore the docs »</strong></a>
    <br />
    <a href="https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym/issues/new?labels=bug&template=bug-report---.md">Report Bug</a>
    &middot;
    <a href="https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym/issues/new?labels=enhancement&template=feature-request---.md">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>
-->

## About The Project
From the specification received upon delivery of the project, it can be seen that the reference domain of the examination is that of the "**Single state problem**", since the solution to our problem can be seen as a sequence of individual actions, and that the action function of the agents takes us from one state to another. In light of this, a solution to the problem will clearly be a _sequence of actions_ (we are therefore in a _complete_, _deterministic_ map state), so the agent capable of solving the problem defined in the specification is a search algorithm.

The aim of the project is to conduct a study of the domain that focuses on implementing a correct solution using artificial intelligence agents, so that the solution is optimal.

With this in mind, an analysis was carried out of the appropriate algorithm classes that have emerged over time, in order to provide an overview of the characteristics that allowed us to reach a final decision on the algorithm to be implemented to solve the given problem (and the respective implementation details).

In light of the considerations contained in `Documents/appunti.md` it was decided to adopt the $A^{\ast} search$ algorithm.

$A^{\ast} search$ is one of the most useful search algorithms in the discipline of single-state domain search (especially informed search). Thanks to this algorithm, instead of sorting the data structure for exploration based on heuristics (directly), we do so based on a function $f(n)$, the sum of the cost and heuristic values $f(n) = g(n) + h(n)$, where the elements of the previous equation can be expressed as: 
-  $g(n)$: current cost to reach $n$;
-  $h(n)$: estimated cost to the goal from $n$;
-  $f(n)$: estimated total cost for the path through $n$ to the goal;

For further information regarding the study conducted on the AI algorithm implemented and the implementation details, please refer to the documents contained in `Documents/appunti.md`.

<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Dependencies installation

Code for the lab of Artificial Intelligence course, Bachelor's degree in Computer Science, University of Verona. 

1. Download [Anaconda](https://docs.anaconda.com/free/miniconda/) for your System.

2. Install Anaconda and Git:
   - On **Linux/Mac**: 
     - `sh Anaconda{version}.sh` to install the Anaconda version chosen.
     - Could be necessary to update your *.bashrc* file writing this line: *export PATH=~/anaconda3/bin:$PATH* then save and close the *.bashrc* file.
     -  Open a terminal and digit: `source ~/.bashrc`
     - Install Git: `sudo apt-get install git` 

   - On **Windows**:
     - Double click the installer to launch.
     - *NB: during the installation, ensure to install "Anaconda Prompt" and use it for the other steps.*
     - Install Git: download [here](https://gitforwindows.org/)

3. Setup Conda environment:
   - `git clone https://github.com/isla-lab/AI_Lab`
   - `cd AI_Lab`
   - `conda env create -f tools/ai-lab-env.yml`

4. To start the environment and start using the project activate the Conda environment with the given instructions, in the root project directory:
   -  `conda activate ai-lab`
   -  jupyter notebook
The last command will open your browser for you to start working.

## Using the Jupyter Notebook

### Jupyter-lab Git integration installation

Below are instructions for installing the Git integration for Jupyter-lab.

_Di seguito sono indicate le istruzioni per l'installazione dell'integrazione Git per Jupyter-lab._

1. Attivare l'ambiente conda _ai-lab_ (```conda activate ai-lab```).
2. Controllare che il kernel Python sia quello giusto, lanciando il comando:
   ```sh
   jupyter kernelspec list
   ```
   e verificando che sia "uguale" a (sufficiente che non sia vuoto):
   ```sh
   python3    /home/andrea-pellizzari/anaconda3/envs/ai-lab/share/jupyter/kernels/python3
   ```
<!--4. Clone the repo:
   ```sh
   git clone https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym
   ```
5. Change the remote URL of git to avoid accidental pushes to the base project:
   ```sh
   git remote set-url origin AndreaPellizzari/AdvancedAquaticDroneOAIGym
   git remote -v # confirm the changes
   ```
6. Setup of module settings based on prerequisites.-->
3. Se il kernel Python non appare, allora vi è un problema con l'env "_ai-lab_".
4. Altrimenti eseguire nella directory dove effettuare il fetch della repo il seguente comando:
   ```sh
   jupyter-lab
   ```
   attivando così _jupyter-lab_ e non _jupyter notebook_.
5. Successivamente, una volta aperta la app di server con _jupyter-lab_, cercare la funzione ```Terminale``` ed eseguire il comando
   ```sh
   conda install -c conda-forge jupyterlab-git
   ```
6. Potrebbe essere utile effettuare i seguenti comandi per effettuare l'accesso su git, se non si è già autenticati:
  ```sh
  git config user.name "Nome Cognome"
  git config user.email "altra@email.com"
  ```
7. A questo punto operare correttamente il fetch della presente repo GitHub ```AndreaPellizzari/AdvancedAquaticDroneOAIGym```, attraverso _import repository_, nella cartella dove si sta eseguendo _jupyter-lab_, attraverso la estensione Git presente nella barra degli strumenti grigia presente a sinistra nella home.

[contributors-shield]: https://img.shields.io/github/contributors/AndreaPellizzari/AdvancedAquaticDroneOAIGym.svg?style=for-the-badge
[contributors-url]: https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym/graphs/contributors

[forks-shield]: https://img.shields.io/github/forks/AndreaPellizzari/AdvancedAquaticDroneOAIGym.svg?style=for-the-badge
[forks-url]: [https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym](https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym)/network/members

[issues-shield]: https://img.shields.io/github/issues/AndreaPellizzari/AdvancedAquaticDroneOAIGym.svg?style=for-the-badge
[issues-url]: https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym/issues

[license-shield]: https://img.shields.io/badge/License-APACHE%202.0-yellow.svg?style=for-the-badge
[license-url]: https://github.com/AndreaPellizzari/marlXAI/blob/main/LICENSE

[product-screenshot]: images/screenshot.png

[java-shield]: https://img.shields.io/badge/Jupyter-red?style=for-the-badge
[sqlite-shield]: https://img.shields.io/badge/Database-SQLite-blue?style=for-the-badge
