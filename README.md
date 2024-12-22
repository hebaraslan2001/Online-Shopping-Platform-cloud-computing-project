# Online-Shopping-Platform-cloud-computing-project
1.	Project Overview:
- This project is an e-commerce platform designed to provide a seamless shopping experience for customers. The platform consists of multiple services handling various functionalities such as user authentication, product catalog management, order processing, and payment processing.

2.	Architecture:
- The Online Shopping Platform is designed to offer a seamless shopping experience through a collection of services. The key services and functionalities include:
  1.	User Management: Handles user authentication. 
  2.	Product Catalog Management: Manages the catalog of products available for purchase.
  3.	Cart Management: Allows users to add, remove, and manage items in their shopping carts.
  4.	Order Processing: Handles the creation, modification, and fulfillment of customer orders.
  5.	Payment Processing: Facilitates secure payment transactions for completed orders.
  These services are designed to be independent, loosely coupled, and communicate with each other via lightweight APIs, primarily using HTTP protocols.



3.	Setup and Installation:
  Technologies Used
- The Online Shopping Platform utilizes the following technologies:
  - Docker: Containerization of services for consistency and ease of deployment.
  - Docker-Compose: Management of multi-container development, staging, and production environments.
  - Kubernetes: Orchestration and efficient management of containerized services for scalability and reliability.
- Dependencies
- Ensure the following dependencies are installed:
  - Docker Engine(dockerfile , dockerimage)
  - Docker-Compose
  - Kubernetes Cluster (for production deployment)


4.	Development Environment:
- Running Locally with Docker Compose
  - docker-compose up
- Accessing the Application
  - Frontend: http://localhost:3000
  - Backend: http://localhost:7249

5.	Deployment:
  Kubernetes Deployment
  1.	Created Docker Images: Build our Docker images.

  2.	Kubernetes Manifests: Use the manifests provided earlier to deploy your services.
  - kubectl apply -f deployment.yml
  3.	Verify Deployment:
  - kubectl get deployments
  - kubectl get pods

- Load Balancing and Fault Tolerance
- Kubernetes services with type ‘LoadBalancer’ will distribute traffic across multiple replicas, ensuring load balancing and fault tolerance.



6.	Scaling and High Availability:
- We used the Horizontal Pod Autoscaler (HPA) to automatically scale your services based on CPU utilization.



7.	API Endpoints:
- Items Service
  - GET /api/ Items/view: Retrieve all products
  - Post /api/ Items/add : Add new items
  - Puts /api/Items/update{id} : update a single items using id
  - Delete /api/Items/delete{id} : delete a single items using id
- Order Service
  - Get /api/order/create order: Create a new order by initialize new id.
  - GET /api/orders/get my order{id} : Retrieve an order by ID.
  - GET /api/orders/get all order : view all order
  - Post /api/order/make order{id} : make a new order by using id and select items you want 
  - Delete api/order/delete order{id} : cancel order and delete all items in this order
  - Delete api/order/delete items from order{id} : delete a single item
From this order by using there ids (id.order,id.item)
- Payment Service
  - post /api/pay/get {id}: pay your items by using id.order and info of visa
