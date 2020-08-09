Vagrant.configure("2") do |config|
N = 2
  # Kubernetes Master Server
  config.vm.define "kmaster" do |kmaster|
    kmaster.vm.box = "centos/8"
    kmaster.vm.hostname = "kmaster.example.com"
    kmaster.vm.network "private_network", ip: "172.42.42.100"
    kmaster.vm.provider "virtualbox" do |v|
      v.name = "kmaster"
      v.memory = 2048
      v.cpus = 2
    end
 end
  NodeCount = 2

  # Kubernetes Worker Nodes
  (1..N).each do |i|
    config.vm.define "kworker#{i}" do |workernode|
      workernode.vm.box = "centos/8"
      workernode.vm.hostname = "kworker#{i}.example.com"
      workernode.vm.network "private_network", ip: "172.42.42.10#{i}"
      workernode.vm.provider "virtualbox" do |v|
        v.name = "kworker#{i}"
        v.memory = 1024
        v.cpus = 1
        end
     end
  end
end