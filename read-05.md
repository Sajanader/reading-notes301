# It's Heroku time!
Open your terminal within your project folder. For my Linux it's:

1. cd /path/to/my/project

Then run:


2. git init
Empty Git repository will be initialized in .git/ folder.```

Then run:

3. git add .
This command allows Git to track your files changes.

Now commit your files to the initialized Git repo:

4. git commit -m "Simple server functionality added"
We'll create our first Heroku application now:

5. heroku create
Heroku will generate a random name for your application. In my case it's enigmatic-citadel-9298. Don't worry. You can change it later.

Now we can deploy our project. Every Heroku app starts with no branches and no code. So, the first time we deploy our project, we need to specify a remote branch to push to:

6. git push heroku master
The application is now deployed. Ensure that at least one instance of the app is running:

heroku ps:scale web=1
And now, before we open it, it's time to choose a proper name for our first creation. I called it myfirstserver:

heroku apps:rename myfirstserver
Everything is done. You can try it now:

7. heroku open
This command will open your Heroku project in your web browser. In this particular case, server address is https://myfirstserver.herokuapp.com/. Now you can share your first web application with any person you want.