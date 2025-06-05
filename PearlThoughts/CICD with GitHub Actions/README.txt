This implements a continuous deployment pipeline for a Yii2 PHP application using:
1.GitHub Actions as CI/CD tool
2.Docker for containerization
3.Docker Hub or GitHub Container Registry for image storage
4.EC2 Instance (with Docker Swarm initialized) for hosting
What in the Pipeline :--
Triggered on push to the main branch
Builds Docker image from the Yii2 PHP app
Pushes the image to Docker Hub
SSHs into your EC2 instance
Pulls the new image
Updates the Docker Swarm service

Directory Structure is placed 

update the Secrets added to GitHub repo:-
EC2_HOST,EC2_USER,EC2_KEY (private SSH key),DOCKER_USERNAME,DOCKER_PASSWORD
How Testing:-
1.Push changes to main branch
2.Check GitHub Actions tab
3.Visit http://<ec2-ip>/ to verify deployment