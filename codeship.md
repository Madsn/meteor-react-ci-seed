# Setup commands
\curl -sSL https://raw.githubusercontent.com/codeship/scripts/master/packages/mongodb.sh | bash -s
curl -o meteor_install_script.sh https://install.meteor.com/
chmod +x meteor_install_script.sh
sed -i "s/type sudo >\/dev\/null 2>&1/\ false /g" meteor_install_script.sh
./meteor_install_script.sh
export PATH=$PATH:~/.meteor/
meteor --version
npm install -g gagarin
meteor npm install

# Test commands
gagarin --verbose