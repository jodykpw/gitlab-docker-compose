# 🐳 GitLab Docker Compose Example

This guide will walk you through the steps to set up GitLab using Docker Compose.

## 🛠️ Prerequisites

- Docker Engine
- Docker Compose

## ⚙️ Domain and IP Whitelist

1. Obtain a registered domain name for accessing the GitLab. This domain will be used to manage the routing and backend services.

2. Configure the domain name to point to the server where you'll be deploying GitLab. This typically involves setting up DNS records, such as an A record or CNAME record, to direct traffic to the appropriate IP address.

3. Additionally, to enforce the IP whitelist, it is recommended to configure your server's firewall or network infrastructure to allow incoming connections only from the specified IP addresses.

## 📚 Usage

1. 📦 Clone the repository:

    ```bash
    git clone https://github.com/jodykpw/gitlab-docker-compose.git
    cd gitlab-docker-compose
    ```
2. ⚙️ Modify the docker-compose.yml file if necessary:

  - Copy the sample `docker-compose.yml.example` file:
   
    ```bash
    cp docker-compose.yml.example docker-compose-prod.yml
    ```

  - If you need to make changes to the Docker Compose file, open it in a text editor and modify the services, ports, volumes, or other configuration options.

  - Refer to the Docker Compose documentation for more details on the available configuration options: https://docs.docker.com/compose/compose-file/

  - If you need to customize the GitLab configuration using gitlab.rb options, you can use the GITLAB_OMNIBUS_CONFIG environment variable.  Refer to the GitLab documentation/gitlab.rb template for more configuration options:

    - https://docs.gitlab.com/omnibus/
    
    - https://gitlab.com/gitlab-org/omnibus-gitlab/blob/master/files/gitlab-config-template/gitlab.rb.template

3. ⚙️ Customize the .env File

- To configure the environment variables for your Traefik Docker Compose setup, you can customize the `.env` file. This file contains key-value pairs that define various settings and parameters used by the containers.

- Follow the steps below to customize the `.env` file:

    3.1 Copy the sample `secrets.env.example` file:

    ```bash
    cp secrets.env.example secrets.env
    ```

    3.2 Update the environment variables in the .env file

4. 🚀  Deploy:

    ```bash
    docker-compose --env-file ./secrets.env -f docker-compose-prod.yml up -d
    ```

## 📄 License

MIT / BSD

## 🇬🇧🇭🇰 Author Information

* Author: Jody WAN
* Linkedin: https://www.linkedin.com/in/jodywan/
* Website: https://www.jodywan.com