# cs1302

This is the repo for CS1302 student notebooks  

- To preview the notebooks with temporary storage, click 
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ccha23/cs1302/main?urlpath=lab%2Ftree%2FLab1%2Fsetup.ipynb)

- To run locally on your computer with permanent storage:
  - Install [docker](
https://docs.docker.com/get-started/#download-and-install-docker).
  - Run the docker in a terminal from a working directory of your choice:  
  ```markdown
  docker run --rm -p 10000:8888 \
           -v "${PWD}":/home/jovyan \
           chungc/cs1302:v0.2 \
           start-notebook.sh --NotebookApp.token=''
  ```
    - It may take a couple minutes to run for the first time as it needs to download the docker image. Subsequent run should be fast.
    - Port 10000 should be free for use. Otherwise, change it to a free port on your computer.
  - Pull the notebooks from this repo in a web browser:  
  <http://localhost:10000/git-pull?repo=https%3A%2F%2Fgithub.com%2Fccha23%2Fcs1302&urlpath=lab%2Ftree%2F%2FLab1%2FSetup.ipynb&branch=main>
    - You can work on the notebooks under the `Lab*` and `Lecture*` subfolders. Clicking the above link again will automatically pull and merge changes from the repo, without overwritting your changes.
    - To finish, stop the notebook server by pressing `Control-C` in the terminal that runs the docker.
    - To restart, run the docker command again from the same working directory.

- To run on a local installation of vscode
  - Install [Visual Studio Code](https://code.visualstudio.com/) and the extension [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).
  - Click `View`->`Command Palette` 
  - Enter `Remote-Containers: Clone Repository in Container Volume...`
  - Enter the repository url `https://github.com/ccha23/cs1302.git`
