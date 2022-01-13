# Create Ansible to do the following

  * Set the timezone to UTC
  * Install NGINX
  * start NGINX and make sure port 80 is listening
  * Your index.html file must contain the string "Sorry for the inconvenience but"

Bonus points will be awarded if the playbook runs on the REDHAT and DEBIAN ansible_os_family.

### sample index.html

````
<!doctype html>
<title>Site Maintenance</title>
<style>
  body { text-align: center; padding: 150px; }
  h1 { font-size: 50px; }
  body { font: 20px Helvetica, sans-serif; color: #333; }
  article { display: block; text-align: left; width: 650px; margin: 0 auto; }
  a { color: #dc8100; text-decoration: none; }
  a:hover { color: #333; text-decoration: none; }
</style>

<article>
    <h1>We&rsquo;ll be back soon!</h1>
    <div>
        <p>Sorry for the inconvenience but we&rsquo;re performing some maintenance at the moment. If you need to you can always <a href="mailto:#">contact us</a>, otherwise we&rsquo;ll be back online shortly!</p>
        <p>&mdash; The Team</p>
    </div>
    <p>
Your server IP address is {{ ansible_hostname }}
</p>
</article>
````

Good Luck

