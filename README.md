Prediction of customers will make online purchase or not based on their age, whether new customer or not, total numner of pages visited. 
1. Trained the ML model
2. Saved and exported the model in .pkl format.
3. Created a Flask app using UI layer.
4. Built a custom Docker image for the app.
5. Ran the app using docker container.
<img width="938" height="504" alt="376363830-066b05b3-f907-4863-b01a-0d651d7a9360" src="https://github.com/user-attachments/assets/24aeb320-fc87-4834-8157-188abb8decdd" />

# Scaling this app by deploying it using Kubernetes
As the next step, we will deploy that app into Google Cloud and scale it using Google Kubernetes Engine.
1. Log in to Google Cloud Account.
2. Enable Artifact Registry API and Kubernetes Engine API.
3. Then open the cloud shell and duplicate this GitHub repo : **git clone https://github.com/hazradeepmoy/CustomerClassification**
4. Then, build a Docker image using the Dockerfile present in the repo.
5. Authenticate Docker configuration using the command : **gcloud auth configure-docker gcr.io**
6. Push the Docker Image to Articaft Registry. We can see the image in the Artifact Registry.
7. Select the computational zone. I have chosen us-central1 : **gcloud config set compute/zone us-central1**
8. Then go to Kubernetes Engine and create a cluster. I have taken node = 1 and zone = us-central1-a
9. Once the cluster is built, deploy the image and expose it to the same port as mentioned in the app.py. In my case, it is 5000.
10. Once it is exposed, we'll get a public IP from where we can run the application.

<img width="1281" height="510" alt="image" src="https://github.com/user-attachments/assets/cb9ef7a3-48c0-4e7e-9193-1ac4e7029aef" />
<img width="1352" height="816" alt="image" src="https://github.com/user-attachments/assets/6ce95d06-8e17-4004-9782-9a616063c50c" />
<img width="1892" height="950" alt="image" src="https://github.com/user-attachments/assets/18ef6b39-1085-43e6-8045-5d6c2e4373ce" />


