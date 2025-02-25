![Mongodb-connection](https://github.com/user-attachments/assets/acb0cb14-5fb6-41b9-abc6-7ab7375660a3)# Container_Orchestration-with-MERN_and_Kubernetes_Helm

Creating Kubernetes deployment files and a HELM chart for a MERN (MongoDB, Express.js, React.js, Node.js) based application.

1. Develop Kubernetes deployment files for both frontend and backend components, ensuring seamless deployment and scalability.
2. Create a HELM chart to streamline the deployment process, allowing for easy configuration and management.
3. Write Jenkins Groovy code to automate the build and deployment process, ensuring consistency and efficiency in your CI/CD pipeline.

# steps to perform -

1. Ceate the Dockerfile for both Frontend and Backend
2. Login into Docker from IDE (vscode) then Build and Push it to Docker Hub.

# commands - 
cd ../learnerReportCS_backend
docker build -t ferocious71/learner-backend:latest .
docker push ferocious71/learner-backend:latest

# Try running the following command inside your local project before building the Docker image:
npm install --legacy-peer-deps

🔹 This forces npm to ignore peer dependency conflicts and install dependencies without breaking.
docker build --no-cache -t ferocious71/learnerreport-frontend .

docker tag ferocious71/learnerreport-frontend ferocious71/learnerreport-frontend:latest
docker push ferocious71/learnerreport-frontend:latest

Resolve the port conflict for both backend and frontend (5000, 3000) respectively.

# check locally if it is running perfectly - 
docker run -p 3000:3000 ferocious71/learnerreport-frontend
docker run -p 5000:5000 ferocious71/learnerreportcs-backend

# configure backend with Mongo db Atlas
create a collection and setup it accordingly to connect to backend.

minikube delete 
minkube start
minikube status

# Apply the Secret to Kubernetes
kubectl apply -f k8s-manifests/

#Then check if it's running:
kubectl get pods


![frontend](https://github.com/user-attachments/assets/18b43e72-7023-4df4-abe9-aefa1392642c)

![backend](https://github.com/user-attachments/assets/ff7f9a1e-f234-42bc-af9e-8b86b3670a8c)

![MongoDB-Atlas](https://github.com/user-attachments/assets/20e12071-6dfc-464f-bbac-2e6f5b96e681)

![minikube service frontend](https://github.com/user-attachments/assets/ed66e500-c17b-4ab3-8677-1bdcea63aba3)

![Mongodb-connection](https://github.com/user-attachments/assets/98cf6bef-25c3-427b-a0e9-30e0822ad7c3)




