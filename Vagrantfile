Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/bionic64"
    config.vm.define "k8s-master" do |server|
        server.vm.provision "Entrypoint", type: "shell", privileged: true, path: "master/entrypoint.sh"
        server.vm.provider "virtualbox" do |vb|
            vb.name = "k8s-master"
            vb.memory = 4096
            vb.cpus = 2
        end
        server.vm.host_name = "k8s-master"
        server.vm.network "public_network", ip: "192.168.0.10"
    end

    config.vm.box = "ubuntu/bionic64"
    config.vm.define "k8s-worker" do |worker|
        worker.vm.provision "Entrypoint", type: "shell", privileged: true, path: "worker/entrypoint.sh"
        worker.vm.provider "virtualbox" do |vb|
            vb.name = "k8s-worker"
            vb.memory = 4096
            vb.cpus = 2
        end
        worker.vm.host_name = "k8s-worker"
        worker.vm.network "public_network", ip: "192.168.0.20"
    end
end
