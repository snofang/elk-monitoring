Vagrant.configure("2") do |config|
  
  # Use the same key for each machine
  config.ssh.insert_key = false

  config.vm.define "es" do |es|
    es.vm.box = "centos/7"
    es.vm.box_version = "1905.1"
    es.vm.box_check_update = false
    #es.ssh.port= "2201"
    #es.vm.network "forwarded_port", guest: 22, host: 2201, id: "ssh"
    es.vm.network "forwarded_port", guest: 9200, host: 9200
    es.vm.network "private_network",  ip: "192.168.10.11"
    es.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "kibana" do |kibana|
    kibana.vm.box = "centos/7"
    kibana.vm.box_version = "1905.1"
    kibana.vm.box_check_update = false
    #kibana.ssh.port= "2202"
    #kibana.vm.network "forwarded_port", guest: 22, host: 2202, id: "ssh"
    kibana.vm.network "forwarded_port", guest: 5601, host: 5601
    kibana.vm.network "private_network",  ip: "192.168.10.12"
    kibana.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "logstash" do |logstash|
    logstash.vm.box = "centos/7"
    logstash.vm.box_version = "1905.1"
    logstash.vm.box_check_update = false
    logstash.vm.network "forwarded_port", guest: 5044, host: 5044
    logstash.vm.network "private_network",  ip: "192.168.10.13"
    logstash.vm.synced_folder ".", "/vagrant", disabled: true
  end

  config.vm.define "filebeat" do |filebeat|
    #filebeat.vm.box = "anandbitra/redhat-6.5"
    #filebeat.vm.box_version = "1.0.0"
    filebeat.vm.box = "centos/7"
    filebeat.vm.box_version = "1905.1"
    filebeat.vm.box_check_update = false
    filebeat.vm.network "private_network",  ip: "192.168.10.14"
    filebeat.vm.synced_folder ".", "/vagrant", disabled: true
  end

end
