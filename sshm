#!/bin/bash

SSH_CONFIG="$HOME/.ssh/config"

# Handle missing config
[[ ! -f "$SSH_CONFIG" ]] && {
    echo "❌ SSH config missing. Creating template..."
    mkdir -p "$HOME/.ssh"
    cat <<EOF > "$SSH_CONFIG"
Host alias1
    HostName real.host.com
    User youruser
EOF
    echo "Done! Add your hosts then rerun."
    exit 1
}

# Extract hosts safely
mapfile -t hosts < <(
    awk '/^[[:space:]]*Host[[:space:]]+[^*]/ {
        for(i=2;i<=NF;i++) print $i
    }' "$SSH_CONFIG" | sort -u
)

[[ ${#hosts[@]} -eq 0 ]] && {
    echo "No valid Host entries found."
    exit 1
}

hosts+=("Quit")

# Colors
RED='\033[0;31m'
GREEN='\033[0;32m'
NC='\033[0m'

while true; do
    clear
    echo -e "${GREEN}🚀 SSH Quick Connect${NC}"
    echo "─────────────────────────────"
    
    for i in "${!hosts[@]}"; do
        if [[ ${hosts[i]} == "Quit" ]]; then
            printf "%2d) ${RED}%s${NC}\n" $((i+1)) "${hosts[i]}"
        else
            printf "%2d) %s\n" $((i+1)) "${hosts[i]}"
        fi
    done
    
    echo "─────────────────────────────"
    read -p "Choose (1-${#hosts[@]}): " choice
    
    if [[ "$choice" =~ ^[0-9]+$ ]] && (( choice >= 1 && choice <= ${#hosts[@]} )); then
        opt="${hosts[$((choice-1))]}"
        
        if [[ "$opt" == "Quit" ]]; then
            echo -e "${GREEN}👋 Goodbye!${NC}"
            exit 0
        fi
        
        echo -e "\n${GREEN}🔗 Connecting to $opt...${NC}"
        
        if ssh -o ConnectTimeout=5 "$opt"; then
            echo -e "\n${GREEN}✅ Session closed${NC}"
        else
            echo -e "${RED}❌ Connection failed${NC}"
        fi
        
        read -n 1 -s -r -p $'\nPress any key...'
        echo
    else
        echo -e "${RED}Invalid choice${NC}"
        sleep 1
    fi
done
