Here are the steps I followed from:
http://www.deploydjango.com/heroku/index.html


1. installation of the tools 
2. created heroku account named: tayhym. Email associated: tayhym@gmail.com
	a. Heroku created SSH key per account
	b. I set tayhym to be default system-wide account
	b2. clone django project from github to desktop.
	c. set django project to use the Heroku account via: cd project_root. heroku accounts:set tayhym
3. Create a Heroku stack, called a cedar stack via: heroku create --stack cedar <nameOfDjangoApp>
	a. resources allocated to each of the processes in the stack can be adjusted heroku ps:scale web-1 worker+2 reports=1
	b. can execute "heroku run python" to get python attached to a shell to run against the application
	note: got back the url, and the git repository hosted on heroku's servers to run
4. If this is the first time running the Heroku instance, generate a new key via "ssh-keygen -t rsa"
    a. or, list all the keys via heroku keys:add
    b. ensure the keys are in the mac's local ssh keys via ssh-add ~/.ssh/id_key
	c. before b, ensure that the permissions on the key files are readonly by owner, via 
	"sudo chmod 600 ~/.ssh/id_key"

	a. if above not working, like it messed up the public key for private key or some wierd error, then generate a new key. via "ssh-keygen -t rsa" 
	b. add the public key identifying me to heroku's servers
	c. heroku keys:add 
	d. git push heroku master (ensure that requirements.txt is present in root directory.)

5. Deploy code to Heroku's servers to run via "git push heroku master"

