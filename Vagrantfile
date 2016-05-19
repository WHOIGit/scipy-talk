Vagrant.configure("2") do |config|
  config.vm.box = "velocity42/xenial64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory="2048"
    vb.cpus="4"
  end
  config.vm.network :forwarded_port, host: 8888, guest: 8888
  config.vm.provision :shell, inline: <<-SHELL
sudo apt-get update
sudo apt-get install -y emacs24-nox
sudo apt-get install -y python-pip ipython-notebook python-skimage fftw3-dev python-lxml python-sklearn python-pandas
sudo pip install pyfftw phasepack
cd /vagrant
cat > ipn <<EOF
ipython notebook --no-browser --ip='*'
EOF
chmod +x ipn
SHELL
end
