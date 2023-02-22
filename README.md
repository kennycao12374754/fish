# fish
#!/bin/bash
sudo apt update
echo "--------------------安装node------------------"
if ! type node >/dev/null 2>&1; then    
    echo 'node 未安装';
    echo "install start!"
    sudo apt install nodejs build-essential -y
    nodejs --version
    sudo apt purge nodejs
    sudo apt autoremove 
    sudo apt install -y curl
    curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -

    node --version
     
    echo "install  success!"
else
    echo 'node 已安装';
fi
npm install -g ironfish 
ironfish chain:download

echo '--------------------安装screen------------------';
if ! type node >/dev/null 2>&1; then
    echo 'screen 未安装'
    echo "install start!"
    apt install screen

    echo "install  success!"
else
    echo 'screen 已安装'
fi

sudo ironfish testnet

