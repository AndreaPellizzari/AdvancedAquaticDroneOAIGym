<a id="readme-top"></a>
[![Contributors][contributors-shield]][contributors-url]
[![Stargazers][stars-shield]][stars-url]
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

<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

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

[stars-shield]: https://img.shields.io/github/stars/AndreaPellizzari/AdvancedAquaticDroneOAIGym.svg?style=for-the-badge
[stars-url]: https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym/stargazers

[issues-shield]: https://img.shields.io/github/issues/AndreaPellizzari/AdvancedAquaticDroneOAIGym.svg?style=for-the-badge
[issues-url]: https://github.com/AndreaPellizzari/AdvancedAquaticDroneOAIGym/issues

[license-shield]: https://img.shields.io/badge/License-APACHE%202.0-yellow.svg?style=for-the-badge
[license-url]: https://github.com/AndreaPellizzari/marlXAI/blob/main/LICENSE

[product-screenshot]: images/screenshot.png

[java-shield]: https://img.shields.io/badge/Jupyter-red?style=for-the-badge
[sqlite-shield]: https://img.shields.io/badge/Database-SQLite-blue?style=for-the-badge
