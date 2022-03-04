Vagrant.configure("2") do |config|
    config.vm.box = "geerlingguy/ubuntu2004"

    config.vm.synced_folder "ansible/", "/ansible"

    config.vm.network "public_network"

    $script = <<-'SCRIPT'
        apt update && apt install ansible -y
        ansible-galaxy install -r /ansible/requirements.yml
        ansible-galaxy collection install community.docker
        ansible-galaxy install geerlingguy.docker
        ansible-playbook /ansible/playbook.yml
    SCRIPT

    config.vm.provision "shell", inline: $script
end