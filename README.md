<h1>Django application, deployment To Heroku</h1>

### Steps:
  1. <b>pip freeze > requirements.txt</b> 📃
  2. At the end of ‘settings.py’ add the following statement  <b>STATIC_ROOT = os.path.join(BASE_DIR, ‘static’)</b> 📂
  3. Install <b>Heroku CLI</b> in your PC and make sure heroku is successfully installed in your system https://www.heroku.com/
  4. Create a file named <b><i>ProcFile with</i></b> <b>*file type</b> and paste this <b><i>web: gunicorn myproject.wsgi</i></b>
  5. After creating ProcFile, replace myproject text with your project name, make sure that you didn't mispell the project name
  6. Now, you are required to install Gunicorn. Install it using python package manager (pip) <b><i>pip install gunicorn</i></b>
  7. run <b>pip freeze > requirements.txt </b> again so that the gunicorn will be added!
  8. Install django-heroku package using <b><i>pip install django-heroku</i></b>
  9. Add imports in your settings.py file <ul><li>import os</li><li>import django_heroku</li></ul>
  10. Activate django_heroku by adding this line at the end of settings.py file <ul><li>
  django_heroku.settings(locals())</li></ul>
  11. Create a copy of your project folder to have backup. In case of error occurs, we can have access to original project.
  12. set DEBUG = FALSE in your settings.py file
  13. Install git. you can refer this link https://positive-stud.medium.com/how-to-download-install-git-for-windows-23ae8c12c5c7
  14. Open git bash from your new project directory and execute following commands <ul><li>git init</li><li>git add .</li><li>git commit -m “deploy”</li><li>heroku login</li></ul>
  15. Create heroku app with your_app_name by running <b>heroku create app_name</b>
  16. Run this command 👉 <b>heroku git:remote -a ravindra-ecommerce</b> that is your heroku app name.
  17. You are required to allocate the allowed hosts or domain which your Django application serves. so add these lines in your settings.py file inside the allowed_hosts section <b>ALLOWED_HOSTS = [‘https://deploy-weather-application.herokuapp.com',
‘localhost’,
‘127.0.0.1’]</b>
  18. Run <b>git push heroku master</b> command
  19. RUN the following commands, <ol><li>heroku run python manage.py migrate</li><li>heroku open</li></ol>
  20.Execute following commands again for reflecting the changes to heroku <ul><li>git add .</li><li>git commit -m “edit”</li><li>git push heroku master</li></ul>
  21. You are DONE. Open your app using heroku open command. Happy Coding 😄😇
  


