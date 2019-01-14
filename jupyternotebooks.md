# Use of jupyter notebooks
You may use the jupyter notebook from your laptop alternatively you can launch an instance on gorina1.ux.uis.no using the following command:

1. open a screen session with screen -S jupyterlab

2. Start the jupyter lab instance using the command "gorina1-jupyter-lab start" and note down the port numbe (port) r which it is running on. This is in the url like this "http://localhost:8888/?token=lskjdflkjslkdjfl"

3. Port forward using "ssh -f -C -q -N -L 8888:localhost:8888 gorina1" (8888 is the port number you got from previous step). It would help to setup passwordless ssh. https://www.tecmint.com/ssh-passwordless-login-using-ssh-keygen-in-5-easy-steps/

4. Now you should be able to access the notebooks using the url "http://localhost:8888/?token=lskjdflkjslkdjfl"

5. If you want to use it form outside UiS network you need to add the following in your ~/.ssh/config 
  Host gorina*
  Hostname %h.ux.uis.no
  User your_unixusername
  ProxyCommand ssh badne7.ux.uis.no nc %h %p 2> /dev/null
  IdentityFile ~/.ssh/id_rsa
  
  
