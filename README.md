# LaragonVirtualHost
laragon-virtualhost-access-chrome

you can change the default in Hostname setting on the preferences page. and yes, the laragon should change the default to something else like .test or .localhost or .devl etc.
I use .loc which is short for .localhost.

=================================================================================
we are free to overcome that mess. many ways :
(1.) Switch to Firefox.
(2.) Change the hostname format.
(3.) enable auto-generated SSL in Laragon

=================================================================================
you may have change your hosts file entries which has .dev TLD to .loc TLD and also do 
change that in your {LaragonRoot}\etc\apache2\sites-enabled or {LaragonRoot}\etc\nginx\
sites-enabled files.

=================================================================================
for many years, we've used .dev for our local sites. Then, Google bought it. Then, they "hard-coded" in Chrome 63 - forces https rediction on. dev domains and causes many troubles.

they have rights to do so but it hurts many developers as well as destroys many articles and videos related to .dev domains. on the other side, we have our freedom to overcome the issue :
if you are stuck with chrome, just change the hostname format in Menu > Preferences to : 
{name}.loc or {name}dev.com or {name}.devl

=================================================================================
you can change it manually to your liking as given here : https://forum.laragon.org/topics/761/chrome-63-now-forces-dev-domains-to-https/2

=================================================================================
just like the .dev gTLD, .app is also the property of Google. Look Here : 
https://icannwiki.org/.app
https://icannwiki.org/.dev
today or tomorrow .app will have the same fate as .dev

=================================================================================
Got fixed like this : 

Clear up the chrome's DNS cache by typing this in the chrome browser
chrome://net-internals/#dns

you will see a button "Clear Host Cache". Press that DNS cache will be flushed.

keep this DNS windows open. now access the virtual host in the browser for me it was 
http://api.localhost. Once you do that you will see a new entry in the DNS window. for me 
it was "localhost." notice the period "." at the end of localhost that showed an error

last step is to simply add this entry as

127.0.0.1 localhost

in the host file located at for ubuntu : /etc/hosts
for windows : C:\Windows\System32\drivers\etc\hosts

another solution could be to ditch the .localhost /.dev at the end of your local virtual host domain

this has to do with some new changes by google. ".dev" and ".local" comes under google's TLD (In the corner of the internet where people care about DNS, there is a bit of an uproar at Google's application for over a hundred new top-level domains, including .dev etc)

Use a domain name you own. Possibly using the full name like "localhost.dev.$yourdomain" could help here on the setup.
