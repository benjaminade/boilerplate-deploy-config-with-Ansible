
# Project: Automated Deployment and Configuration with Ansible for Boilerplates
    Overview
    This project involves automating the deployment and configuration of a boilerplate application using Infrastructure as Code (IaC) with Ansible. The main tasks include cloning a repository, installing dependencies, configuring a PostgreSQL database, setting up a messaging queue, configuring the application and Nginx, and setting up logging.

# Project Structure
    The project comprises a main.yaml file which is the Ansible playbook that performs all the tasks.

    Then we now have roles which are directories containing Ansible roles for organizing tasks.

    For this task, i have the following roles:
     roles:
    - common
    - clone-repo
    - dependencies-and-packages
    - virtual-environment
    - postgres
    - app
    - deny-port-3000-externally
    - nginx
# Requirements
    1. A remote Linux server (Ubuntu 22.04).
    2. Ansible installed on the control machine.
    3. Access to the devops branch of the boilerplate repository in the hngprojects GitHub workspace.
    This is the repo url : https://github.com/hngprojects/hng_boilerplate_python_fastapi_web


# Instructions

    1. User and Directory Setup
    Create User hng: The playbook will create a user named hng with sudo privileges.

    Clone Repository: Clone the devops branch of your boilerplate repository into the /opt directory of the remote server with the name stage_5b and ensure it is owned by the hng user.

    2. Database and Dependencies
    Install PostgreSQL: Install PostgreSQL and save the admin credentials in /var/secrets/pg_pw.txt.

    Install Dependencies: Install all application dependencies, including databases and messaging queues, and configure the environment variables, application properties, or application settings accordingly.

    3. Application and Proxy Setup
    Run Application: Ensure the application is running on 127.0.0.1:3000 without exposing port 3000 externally.
    
    Install Nginx: Install Nginx 1.26 and configure it to reverse proxy requests from port 80 to your application.
    4. Logging Configuration
    Setup Logging: Configure stderr logs to be saved in /var/log/stage_5b/error.log and stdout logs in /var/log/stage_5b/out.log, with both files owned by the hng user.

