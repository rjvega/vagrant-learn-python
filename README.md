#vagrant-learn-python

1. cd /home/vagrant/test
2. source bin/activate
3. hostname -I  #get the VM's IP address
4. cd mysite
5. add VM's IP address in settings.py
#--------------------------------------------------------------------------
ALLOWED_HOSTS = ["0.0.0.0","192.168.65.86","192.168.0.22","192.168.59.171"]
#--------------------------------------------------------------------------
6. run the server
python manage.py runserver <VMs IP addr>:8000

I'm currently going through this tutorial
https://docs.djangoproject.com/en/1.10/intro
