<h1 style="text-align:center"><a href="https://fit.dhcn.vn">FIT - HaUI</a></h1>
<h2><b>MAKE FOLDER</b></h2>
<p>CODE: /home/dll/dfit/code</p>
<p>DNN: /home/dnn/fit</p>
<p>SETUP: /home/setup</p>
<hr/>
<h3><b>1. HOST:</b></h3>
<div>
    <p><i>add host /etc/hosts</i></p>
    <p><code>127.0.0.1   f.dhcn.vn i.dhcn.vn</code></p>
</div>
<hr/>
<h3><b>2. NGINX:</b></h3>
<div>
    <p><i>add nginx.conf /etc/nginx/nginx.conf</i></p>
    <p><code>/home/dll/dfit/code/config/nginx/development/*.conf</code></p>
</div>
<hr/>
<h3><b>3. DOWNLOAD AND SETUP:</b></h3>
<div>
    <div>
        <h5>3.1 MAKE FOLDER /home/setup</h5>
        <p><code>mkdir /home/setup -p</code></p>
        <p><code>cd /home/setup</code></p>
        <p><code>chmod -R 777 /home/setup</code></p>
    </div>
    <hr/>
    <div>
        <h5>3.2 PYTHON 3.9.4</h5>
        <p><i>Download <a target="_blank" href="https://fit.dhcn.vn/setup/Python-3.9.4.tar.xz">Python-3.9.4.tar.xz</a></code></p>
        <p><code>wget https://fit.dhcn.vn/setup/Python-3.9.4.tar.xz</code></p>
        <p><code>tar -xf Python-3.9.4.tar.xz</code></p>
        <p><code>cd Python-3.9.4 && ./configure && make && make install</code></p>
    </div>
    <hr/>
    <div>
        <h5>3.3 MONGO 5</h5>
        <p><i>Download <a target="_blank" href="https://fit.dhcn.vn/setup/mongo5.tar">mongo5.tar</a></i></p>
        <p><code>wget https://fit.dhcn.vn/setup/mongo5.tar</code></p>
        <p><code>tar -xf mongo5.tar</code></p>
    </div>
    <hr/>
    <div>
        <h5>3.4 PYCHARM</h5>
        <p><i>Download <a target="_blank" href="https://fit.dhcn.vn/setup/pycharm-professional-2021.2.3.tar.gz">pycharm-professional-2021.2.3.tar.gz</a></i></p>
        <p><code>wget https://fit.dhcn.vn/setup/pycharm-professional-2021.2.3.tar.gz</code></p>
        <p><code>tar -xf pycharm-professional-2021.2.3.tar.gz</code></p>
        <p><code>cd pycharm-2021.2.3/bin</code></p>
        <p><code>./pycharm.sh</code></p>
    </div>
    <hr/>
    <div>
        <h5>3.5 LIBREOFFICE</h5>
        <p><i>Download <a target="_blank" href="https://fit.dhcn.vn/setup/LibreOffice_7.3.1_Linux_x86-64_rpm.tar.gz">LibreOffice_7.3.1_Linux_x86-64_rpm.tar.gz</a></i></p>
        <p><code>wget https://fit.dhcn.vn/setup/LibreOffice_7.3.1_Linux_x86-64_rpm.tar.gz</code></p>
    </div>
</div>
<hr/>
<h3><b>4. YUM INSTALL:</b></h3>
<div>
    <p><i>run sh && yum</i></p>
    <p><code>cd /home/dll/dfit/code/setup</code></p>
    <p><code>$ ./setup.sh</code></p>
</div>
<hr/>
<h3><b>5. VIRTUALENV:</b></h3>
<div>
    <p><i>create virtualenv <b>lfit</b></i></p>
    <p><code>$ cd /home && virtualenv -p /usr/local/bin/python3.9 /home/lfit</code></p>
    <p><code>$ source /home/lfit/bin/activate</code></p>
</div>
<hr/>
<h3><b>6. UPDATE PIP:</b></h3>
<div>
   <p><code>$ /home/lfit/bin/python -m pip install --upgrade pip</code></p>
   <p><code>$ pip install -r /home/dll/dfit/code/requirements.txt</code></p>
</div>
<hr/>
<h3><b>7. PIP INSTALL PYTHON LIBRARY:</b></h3>
<div>
   <p><code>$ cd /home/dll/dfit/code/setup/pycrypto-2.6.1</code></p>
   <p><code>$ python setup.py install</code></p>
   <p><i>REQUIREMENTS</i></p>
   <p><code>$ cd /home/dll/dfit/code/setup</code></p>
   <p><code>$ /home/lfit/bin/pip install fit-2022.2.15-cp39-cp39-linux_x86_64.whl --force-reinstall</code></p>
</div>
<hr/>
<h3><b>8. SETTING CONFIG:</b></h3>
<div>
   <p><code>account: mysql, mongo</code></p>
   <p><code>mysql_secure_installation   root/1234567</code></p>
   <p><code>mongo-account   empty/empty</code></p>
</div>
<hr/>
<h3><b>9. START SERVICE:</b></h3>
<div>
   <p><code>service mariadb restart</code></p>
   <p><code>service nginx restart</code></p>
</div>
<hr/>
<h3><b>10. INSTALL DATABASE:</b></h3>
<div>
   <p><code>mongo:  meo_fit_dhcn_vn</code></p>
   <p><b>mysql:  /database/fit_data.sql</b></p>
   <p><code>cd /home/dll/dfit/code/database && mysql -uroot -p1234567 fit_data < fit_data.sql</code></p>
</div>
<hr/>
<h3><b>11. EDIT SETTING CONFIG:</b></h3>
<div>
   <p><code>/home/dll/dfit/code/config/development/f.dhcn.vn.json</code></p>
</div>
<hr/>
<h3><b>12. USER LOGIN DEFAULT:</b></h3>
<div>
   <p><code>username: admin</code></p>
   <p><code>password: abc@123</code></p>
</div>
<hr/>
<h3><b>13. CONFIG AND RUN ON PYCHARM:</b></h3>
<div>
    <p><i>dmain.py</i></p>
    <p>
        <code>scrippath       /home/dll/dfit/code/dmain.py</code>
        <code>paramaters      -a f.dhcn.vn -m main -p 1</code>
        <code>working drectory /home/dll/dfit/code</code>
    </p>
    <p><i>dopen.py</i></p>
    <p>
        <code>scrippath       /home/dll/dfit/code/dopen.py</code>
        <code>paramaters      -a f.dhcn.vn -m open -p 1</code>
        <code>working drectory /home/dll/dfit/code</code>
    </p>
</div>