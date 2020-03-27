---
layout: post
title: Flask Plugins
slug: flask-plugins
author: Martin Thoma
date: 2019-12-31 20:00
category: Code
tags: Flask
featured_image: logos/flask.png
---
The Flask Ecosystem has [a lot of extensions](http://flask.pocoo.org/extensions/).
I'll introduce a couple I've stumbled over. There is also an [awesome list](https://github.com/humiaozuzu/awesome-flask), but it contains too many extensions and too little
explanation when to use what.

<div class="info">This is an article I had for quite a while as a draft. As part of my yearly cleanup, I've published it without finishing it. It might not be finished or have other problems.</div>

## Databases

[`Flask-SQLAlchemy`](https://flask-sqlalchemy.palletsprojects.com/en/2.x/) and
[`Flask-Migrate`](https://flask-migrate.readthedocs.io/en/latest/) (Alembic)
are pretty much standard. The first one is a binding to the de-facto standard
ORM in Python (SQLAlchemy) and the second one is for creating Migrations with
Alembic.


## REST API

[Flask-RESTX](https://flask-restx.readthedocs.io/en/stable/) is good
for creating nice REST APIs. It also generates a swagger page 🙂

[flask-restless](https://flask-restless.readthedocs.io/en/stable/index.html)
works directly on the models. I haven't used it so far.

Worse alternatives:

* Flask-Restful: [No autogenerated Swagger](https://stackoverflow.com/a/41783739/562769)


## Forms

[Flask-WTF](https://flask-wtf.readthedocs.io/en/stable/) is for creating forms,
including CSRF, file upload, and reCAPTCHA.


## E-Mail

[Flask-Mail](https://pythonhosted.org/Flask-Mail/) provides a simple interface
to set up SMTP with your Flask application and to send messages from your views
and scripts.


## Role Management

[Flask-Principal](https://pythonhosted.org/Flask-Principal/)


## User management

[Flask-Login](https://flask-login.readthedocs.io/en/latest/) provides user
session management for Flask. It handles the common tasks of logging in,
logging out, and remembering your users’ sessions over extended periods of
time.

Here is a usage example:

```python
from flask_login import LoginManager
from flask_login import current_user, login_user, login_required, logout_user

login_manager = LoginManager()
login_manager.login_view = "auth.login"


@login_manager.user_loader
def load_user(id):
    return User.query.get(int(id))


@login_required
@app.route("/private")
def some_private_view():
    return "You can only watch this if you're logged in"


@auth.route("/login", methods=["GET", "POST"])
def login():
    if current_user.is_authenticated:
        return redirect(url_for("main.index"))
    form = LoginForm()  # You have to create LoginForm on your own
    if form.validate_on_submit():
        user = User.query.filter_by(email=form.email.data).first()
        if user is None or not user.check_password(form.password.data):
            flash("Invalid email or password", "error")
            return redirect(url_for("auth.login"))
        login_user(user, remember=form.remember_me.data)
        return redirect(url_for("some_private_view"))
    return render_template("login.html", form=form)


@auth.route("/logout")
@login_required
def logout():
    logout_user()
    return redirect(url_for("main.index"))


@auth.route("/register", methods=["GET", "POST"])
def register():
    if current_user.is_authenticated:
        return redirect(url_for("main.index"))
    form = RegistrationForm()  # You have to write RegistrationForm on your own
    if form.validate_on_submit():
        user = User(email=form.email.data)
        user.set_password(form.password.data)
        db.session.add(user)
        db.session.commit()
        user = User.query.filter_by(id=user.id).first_or_404()
        user.display_name = "user_{}".format(user.id)
        db.session.commit()
        flash("Congratulations, you are now a registered user!")
        return redirect(url_for("auth.login"))
    return render_template("register.html", form=form)
```


There is also [Flask-User](https://flask-user.readthedocs.io/en/latest/) and Flask-Security which both offer you to give you
the following:

* Registration
* Forgotten Password
* Login / Logout

Instead of using those, you might want to combine Flask-Principal, Flask-Login,
Flask-Mail.


## SocketIO

[Flask-SocketIO](https://flask-socketio.readthedocs.io/en/latest/)

## Translations

[Flask-Babel](https://pypi.org/project/Flask-Babel/)


## Also

* [Flask-Security](https://pythonhosted.org/Flask-Security/)
* [Flask-User](https://flask-user.readthedocs.io/en/latest/)