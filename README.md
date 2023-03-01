# Kos_Legacy_Codespace
Simple repo to launch Kos with legacy toolchain in Codespaces 

Test

# Tips:
  * Helper commands to launch in the Terminal (inside your codespace: File-View-Terminal):
    * To add the Kos examples to your VSCode workspace:
      * code -a /opt/toolchains/dc/kos/examples
    * To go to the kos folder:
      * cd /opt/toolchains/dc
    * To compile an example & send the .elf to your broadband adapter (BBA): something like:
      * cd /opt/toolchains/dc/kos/examples/dreamcast/hello
      * make
      * dc-tool-ip -t 192.168.1.200 -x hello.elf
        * (with 192.168.1.200 being the ip address of your BBA)
        * Notes:
          * By default, Codespaces can only access the BBA if it is reachable via the internet (ie, addresses like 192.168.0.xxx, 192.168.1.xxx or 10.0.0.xxx, ... are not reachable)
          * If you want Codespaces to be able to access the BBA when it is only reachable via your internal network, [check this link](https://docs.github.com/en/codespaces/developing-in-codespaces/connecting-to-a-private-network)
  * When you have finished working with your codespace, click on the green "Code" button again, and on the 3 dots next to your codespace to stop your container from running. This will save you some free execution minutes (default idle timeout is 30 minutes, and you get [120 free core hours per month](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts)).
