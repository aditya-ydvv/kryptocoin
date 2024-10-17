# Kryptocoin

Kryptocoin is a cryptocurrency-related website built using the Flask framework. This project serves as a platform for managing cryptocurrency-related data, transactions, or information.

## Website
You can visit the live website at: [Kryptocoin](https://kryptocoin.pythonanywhere.com/)

![Website Snapshot](/Screenshot.png)

## Features
- Cryptocurrency tracking
- User authentication
- Real-time data fetching
- Responsive web interface

## Requirements
Before setting up the project, make sure you have the following installed on your machine:
- Python 3.7+
- pip (Python package manager)
- Virtualenv (optional, but recommended)

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/kryptocoin.git
cd kryptocoin
```

### 2. Create and Activate a Virtual Environment
It’s recommended to use a virtual environment to keep dependencies isolated.

# On macOS/Linux
```bash
python3 -m venv venv
source venv/bin/activate
```

```bash
# On Windows
python -m venv venv
venv\Scripts\activate
```
### 3. Install Dependencies
Use pip to install all necessary Python packages:

```bash
pip install -r requirements.txt
```

### 4. Set Up Environment Variables
Create a .env file in the root of the project and add your environment variables, such as Flask settings, secret keys, and any other configurations:

```bash
FLASK_APP=run.py
FLASK_ENV=development
SECRET_KEY=your-secret-key
```

### 5. Initialize the Database (if applicable)
If your project uses a database, run migrations or any initialization commands:

```bash
flask db init
flask db migrate
flask db upgrade
```

### 6. Run the Application
Start the Flask development server:

```bash
flask run
```
Visit the site in your browser at `http://127.0.0.1:5000/`.

### 7. Running Tests (Optional)
If you have unit tests or integration tests, you can run them using:

```bash
pytest
```

## Deployment
For deployment, you can use platforms like Heroku, PythonAnywhere, or any cloud provider that supports Flask applications. Make sure to configure the environment variables and database settings in the production environment.

To deploy Kryptocoin on PythonAnywhere, follow these steps:

### 1. Sign Up / Log In to PythonAnywhere
- If you don’t already have a PythonAnywhere account, sign up at [https://www.pythonanywhere.com/](https://www.pythonanywhere.com/).
- Log in if you already have an account.

### 2. Upload Your Project Files
You can upload your project in one of the following ways:

- **Using Git:** Push your project to GitHub, and then clone it on PythonAnywhere:
   ```bash
   git clone https://github.com/your-username/kryptocoin.git
   ```
- **Manual Upload:** Alternatively, you can upload files directly using PythonAnywhere's web interface.

### 3. Create a Virtual Environment on PythonAnywhere
1. Open the **Bash Console** in PythonAnywhere.
2. Navigate to your project directory:
   ```bash
   cd kryptocoin
    ```
3. Create a virtual environment:
    ```bash
    python3 -m venv venv
    ```
4. Activate the virtual environment:
    ```bash
    source venv/bin/activate
    ```
5. Install your dependencies:
    ```bash
    pip install -r requirements.txt
    ```

### 4. Configure the Web App
1. Go to the Web tab on PythonAnywhere and click Add a new web app.
2. Choose Manual Configuration and select Flask with Python 3.x.
3. Set the working directory to your project folder (/home/your-username/kryptocoin).
4. Configure the WSGI file:
    - Click on the WSGI file link in the web app section (it looks something like `/var/www/your-username_pythonanywhere_com_wsgi.py`).
    - Modify the WSGI file to point to your Flask app. It should look like this:
        ```bash
        import sys
        import os

        # Add your project directory to the sys.path
        project_home = '/home/your-username/kryptocoin'
        if project_home not in sys.path:
            sys.path.append(project_home)

        # Activate your virtualenv
        activate_this = '/home/your-username/kryptocoin/venv/bin/activate_this.py'
        with open(activate_this) as file_:
            exec(file_.read(), dict(__file__=activate_this))

        # Import Flask app
        from run import app as application
        ```
        Replace your-username with your actual PythonAnywhere username.
5. Save and close the file.

### 5. Set Environment Variables
In the Web tab, under the Environment Variables section, set any necessary environment variables (e.g., `FLASK_ENV`, `SECRET_KEY`). You can do this by adding key-value pairs like:

```Bash
FLASK_ENV=production
SECRET_KEY=your-secret-key
```

### 6. Restart the Web App
After configuring everything, scroll to the top of the Web tab and click the Reload button to restart your app.

### 7. Check Your App
Visit the live link to your website (it will be something like `https://your-username.pythonanywhere.com/`), and your Flask app should now be running on PythonAnywhere.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.