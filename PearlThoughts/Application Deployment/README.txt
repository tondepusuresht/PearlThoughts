This project,how to deploy a PHP application using Docker Swarm on an AWS EC2 instance, with NGINX running outside Docker (on the host machine) as a reverse proxy.
Stack Overview:-
1.Docker Swarm – used to orchestrate the service
2.NGINX (host-based) – reverse proxy to the Docker container
3. EC2 Instance (Amazon Linux) – hosting environment
Prerequisites:-
1.EC2 instance (Amazon Linux )
2.Docker & Docker Swarm installed and initialized
3.NGINX installed and running on the EC2 host
4. Open ports 80 (HTTP) and optionally 443 (HTTPS)
SourceCode:
clone the php source code using GIT

Host-Based NGINX Reverse Proxy:-
1.copy to nginx to file to in server(etc/nginx/conf.d/)
2. Then reload NGINX using
 sudo nginx -t && sudo systemctl reload nginx

Build and Deploy the App:-
# Build the image locally (optional if using CI)
docker build -t yourdockerhubuser/php-app:latest -f docker/Dockerfile .

# Push to Docker Hub
docker push yourdockerhubuser/php-app:latest

# Initialize Docker Swarm (if not done)
docker swarm init

# Deploy stack
docker stack deploy -c swarm/stack.yml phpapp
Test:
browse public IP 


