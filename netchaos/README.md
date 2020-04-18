# This folder is meant to be used from the netchaos script

## Download and execute netchaos

`curl -sSL https://raw.githubusercontent.com/0xtf/training-scripts/master/netchaos/netchaos -o /tmp/netchaos && chmod +x /tmp/netchaos && /tmp/netchaos`

## One liner to display unique IPs involved in Suricata alerts

`echo -e "\nSource IPs:\n" && cat /var/log/suricata/eve.json | jq -r -c 'select(.event_type=="alert")|.src_ip'|grep 10.0 | more | uniq && echo -e "\nDestination IPs:\n" && cat /var/log/suricata/eve.json | jq -r -c 'select(.event_type=="alert")|.dest_ip'|grep 10.0 | more | uniq && echo ""`
