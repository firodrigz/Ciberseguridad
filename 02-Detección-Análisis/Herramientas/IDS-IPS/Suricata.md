Puede funcionar como IDS o IPS

### Instalación

- sudo apt purge suricata -> Elimina por completo un programa
- sudo add-apt-repository ppa:oisf/suricata-stable
- sudo apt install suricata
- sudo systemctl status suricata

### Configuración

- sudo nano /etc/suricata/suricata.yaml
interface: eth0

- HOME_NET
- default-log-dir: /var/log/suricata
- default-rule-path:  /usr/share/suricata/rules
- rule-files: 
	- suricata.rules
	- suricata.rules 

- sudo suricata-update
- cd /usr/share/suricata/rules/   -> se pueden ver ejemplos de cómo se arman las reglas
- sudo systemctl restart suricata
- tail -f /var/log/suricata/fast.log