FROM registry.redhat.io/ansible-tower-37/ansible-tower-rhel7:3.7.1
USER root
RUN mkdir -p /var/lib/awx/venv/ansible_with_modules
RUN virtualenv --system-site-packages /var/lib/awx/windows_modules
RUN cp -a /var/lib/awx/venv/ansible/lib64/python.2.7/site-packages* /var/lib/awx/venv/windows_modules/lib64/python2.7/site-packages
RUN sh -c ". /var/lib/awx/venv/windows_modules/bin/activate ; pip3 install pywinrm"
RUN sh -c ". /var/lib/awx/venv/windows_modules/bin/activate ; pip3 install ptwinrm"
RUN sh -c ". /var/lib/awx/venv/windows_modules/bin/activate ; pip3 install pysnow"
RUN sh -c ". /var/lib/awx/venv/windows_modules/bin/activate ; pip3 install netaddr"
