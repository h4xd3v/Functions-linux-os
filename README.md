# Functions-linux-os

Colores y funciones para E.H
```bash
#Colours
declare -r greenColour="\e[0;32m\033[1m"
declare -r endColour="\033[0m\e[0m"
declare -r redColour="\e[0;31m\033[1m"
declare -r blueColour="\e[0;34m\033[1m"
declare -r yellowColour="\e[0;33m\033[1m"
declare -r purpleColour="\e[0;35m\033[1m"
declare -r turquoiseColour="\e[0;36m\033[1m"
declare -r grayColour="\e[0;37m\033[1m"

function mkt()
{
  echo -ne "\n${yellowColour}[!] dis = Discovery (nmap, gobuster, nikto, SurfaceWeb) ${endColour}"
  echo -ne "\n${blueColour}[*] cont = Content (Files DeepWeb) ${endColour}"
  echo -ne "\n${redColour}[+] exp = Exploits (github, CVEs) ${endColour}\n\n"
  mkdir {dis,cont,exp}
}

function target()
{
  echo "$1" >  /home/h4x/Documents/HTB/target.txt
  echo "$1" | xclip -sel clip
}

function xtarget()
{
  cat /home/h4x/Documents/HTB/target.txt | xclip -sel clip
}

function xhip()
{
  ip a | grep -i tun0 | grep -E "inet .*" | grep -oP '[0-9]{1,4}.[0-9]{1,4}.[0-9]{1,4}.[0-9]{1,4}' | xclip -sel clip
}
```
