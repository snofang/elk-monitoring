Vagrant.configure("2") do |config|
  
  # Use the same key for each machine
  config.ssh.insert_key = false

  config.vm.define "elasticsearch" do |elasticsearch|
    elasticsearch.vm.box = "centos/7"
    elasticsearch.vm.box_version = "1905.1"
    elasticsearch.vm.network "forwarded_port", guest: 22, host: 2201, id: "ssh"
    elasticsearch.vm.network "forwarded_port", guest: 9200, host: 9200
  end

  config.vm.define "kibana" do |kibana|
    kibana.vm.box = "centos/7"
    kibana.vm.box_version = "1905.1"
    kibana.ssh.port= "2202"
    kibana.vm.network "forwarded_port", guest: 22, host: 2202, id: "ssh"
    kibana.vm.network "forwarded_port", guest: 5601, host: 5601
  end


end
