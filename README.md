## Running the applcations

Create python virtual environment.

```bash
python3 -m venv venv-app
```

Open a second terminal window and enable this virtual environment in both terminal windows.

```bash
source venv-app/bin/activate
```

Install python requirements.

```bash
pip3 install -r requirements.txt
```

Run app1 in the first terminal window.

```bash
python3 app1/app.py
```

You should see that app1 is now running on localhost port 5001

```bash
* Serving Flask app 'app'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5001
```

Run app2 in the second terminal window.

```bash
python3 app2/app.py
```

You should see that app2 is now running on localhost port 5002

```bash
* Serving Flask app 'app'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5002
```

Open a web browser and go to http://localhost:5001 to access app1. Notice that you've been redirected to the /login page. Try to access http://localhost:5001/printhello and notice that you've been redirected to the login page again.

Open a private browser tab and go to http://localhost:5002 to access app2. Notice that you've been redirected to the /login page.

Click ``Login`` link in app1 browser tab and follow the authentication process in Azure AD. After that you will be redirected to the app1 index page where you can access app2.

If you will click ``Launch app2`` you will bypass authentication in Azure AD since user has been already athenticated through app1.

To test authentication in app2 separately use private browser tab where http://localhost:5002 is opened and try access the ``Login`` link to go through the same process.

After following ``Launch app2`` link notice that you've been redirected to http://localhost:5002 where ``PrintHello`` link is available.

Once you click ``PrintHello`` link you will be redirected back to http://localhost:5001/printhello (app1) and will see the ``Hello`` message.