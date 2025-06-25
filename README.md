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

#--Custom HTB IP                                                                        
VPN_IP=$(ip a show tun0 | grep inet | awk {'print $2}' | head -n 1 | grep -oP '\b(?:[0-9]{1,3}\.){3}[0-9]{1,3}\b')
if [ -z "$VPN_IP" ]; then         
    VPN_IP="down-ip"                     
fi                                
# Agregar la verificación de IP de la VPN (tun0) al prompt
VPN_IP=$(ip a show tun0 | grep inet | awk {'print $2}' | head -n 1 | grep -oP '\b(?:[0-9]{1,3}\.){3}[0-9]{1,3}\b')
                                            
if [ -z "$VPN_IP" ]; then
    VPN_IP="down-ip"                                                                                                                                                             
fi                                                                                      
                                                                                        
# Modificar el prompt (PS1)
if [ "$color_prompt" = yes ]; then
    PS1="\[\033[0;31m\]\342\224\214\342\224\200\$([[ \$? != 0 ]] && echo \"[\[\033[0;37m\]\342\234\227\[\033[0;31m\]]\342\224\200\")[$(if [[ ${EUID} == 0 ]]; then echo '\[\033[0
1;31m\]root\[\033[01;33m\]@\[\033[01;96m\]\h'; else echo '\[\033[0;39m\]\u\[\033[01;33m\]@\[\033[01;96m\]\h'; fi)\[\033[0;31m\]]\342\224\200[\[\033[0;32m\]\w\[\033[0;31m\]]─[$VP
N_IP]\n\[\033[0;31m\]\342\224\224\342\224\200\342\224\200\342\225\274 \[\033[0m\]\[\e[01;33m\]\\$\[\e[0m\]"
else                                                                                    
    PS1='┌──[\u@\h]─[\w]─['$VPN_IP']\n└──╼ \$ '
fi                                          
                                            
#--- 

```
# Herramientas
- Zellij
- Tmux (Oh my tmux)
  
# Arbol de archivos
```bash
sudo mkdir {/opt/AD,/opt/Web,/opt/Movil/,/opt/ExecWindows,/opt/ExecLinux}
```
/opt/AD
/opt/Web
/opt/Movil
/opt/ExecWindows
/opt/ExecLinux
