# pangu
## Installation
The following is the steps to install the application.

1. Download the source code:

   ```
   git clone https://github.com/dirkxu/pangu.git
   ```
2. Change the hosts file to point the domain to your server.
   - Windows: `c:\Windows\System32\Drivers\etc\hosts`
   - Linux: `/etc/hosts`

   Add the following lines:

   ```
   127.0.0.1   yourdomain.dev
   127.0.0.1   yourdomain.dev
   ```
3. Set document roots of your web server:
   For Apache it could be the following:

   ```apache
   <VirtualHost *:80>
       ServerName yourdomain.dev
       DocumentRoot "/usr/local/httpd2.2/htdocs/pangu/web/"
       ErrorLog "logs/pangu.com-error_log"
       CustomLog "logs/pangu.com-access_log" common

       <Directory "/usr/local/httpd2.2/htdocs/pangu/web/">
           RewriteEngine on
           RewriteCond %{REQUEST_FILENAME} !-f
           RewriteCond %{REQUEST_FILENAME} !-d
           RewriteRule . index.php
           DirectoryIndex index.php
       </Directory>
   </VirtualHost>
   ```

Then, you can view the page in browser with the following url:
   ```
   http://yourdomain.dev/
   ```

