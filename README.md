# Kos_Legacy_Codespace
Simple repo to launch Kos with legacy toolchain in [Codespaces](https://www.youtube.com/watch?v=sYJ3CHtT6WM)

To launch it from github, just click on the "<> Code" button, then "Codespaces" - "Create codespace on main".

# Notes for [KallistiOS](https://github.com/KallistiOS/KallistiOS):
  * __kos__: the latest version has been downloaded and compiled.
    * To go to the kos folder:
      * cd /opt/toolchains/dc
    * To compile a kos example, eg the hello example:
      * source /opt/toolchains/dc/kos/environ.sh
      * cd /opt/toolchains/dc/kos/examples/dreamcast/hello
      * make
  * __kos-ports__: the latest version has been downloaded, but needs compiling - this takes 3-4 minutes:
    * cd /opt/toolchains/dc/kos-ports/utils
    * source /opt/toolchains/dc/kos/environ.sh
    * ./build-all.sh
  * __dc-tool-ip__: the latest version has been downloaded and compiled.
    * By default, Codespaces can only access your Dreamcast's Broadband Adapter (BBA) if it is reachable via the internet (ie, addresses like 192.168.0.xxx, 192.168.1.xxx or 10.0.0.xxx, ... are not reachable)
    * If you want Codespaces to be able to access the BBA when it is only reachable via your internal network, [check this link](https://docs.github.com/en/codespaces/developing-in-codespaces/connecting-to-a-private-network)
    * to send an .elf executable to a BBA:
      * dc-tool-ip -t 1.2.3.4 -x hello.elf
      * (with 1.2.3.4 being the ip address of your BBA)


# Tips:
  * Helper commands to launch in the Terminal (inside your codespace: File-View-Terminal):
    * To add the Kos examples to your VSCode workspace:
      * code -a /opt/toolchains/dc/kos/examples

  * When you have finished working with your codespace, click on the green "Code" button again, and on the 3 dots next to your codespace to stop your container from running. This will save you some free execution minutes (default idle timeout is 30 minutes, and you get [120 free core hours per month](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts)).

# Tips:
  * Helper commands to launch in the Terminal (inside your codespace: File-View-Terminal):
    * To add the Kos examples to your VSCode workspace:
      * code -a /opt/toolchains/dc/kos/examples
  * When you have finished working with your codespace, click on the green "Code" button again, and on the 3 dots next to your codespace to stop your container from running. This will save you some free execution minutes (default idle timeout is 30 minutes, and you get [120 free core hours per month](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts)).
  * When launching your codespace for a 2nd time, be sure to do a git pull at the start inside your codespace to be in line with your repo, it will save you some problems.
  
# If you want to use Codespaces in your own github repository
* Copy the contents of the ".devcontainer" folder into your repo:
  * at least the "devcontainer.json" file,
  * and if you want to add extra stuff to a pre-built Docker image, also add the Dockerfile.
