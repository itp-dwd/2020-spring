# Database Services Guide

## About

This is a guide to some database services that can be a database hosting service. 

## Table of Contents

- [Database Services Guide](#database-services-guide)
  - [About](#about)
  - [Table of Contents](#table-of-contents)
  - [Services](#services)
  - [MongoDB Atlas](#mongodb-atlas)
    - [What is MongoDB Atlas?](#what-is-mongodb-atlas)
    - [Setting up MongoDB Atlas](#setting-up-mongodb-atlas)
      - [Register](#register)
      - [Create a new project](#create-a-new-project)
      - [Create a cluster](#create-a-cluster)
      - [Manage your connections](#manage-your-connections)
      - [Choosing a connection method](#choosing-a-connection-method)
  - [Firebase:](#firebase)

## Services

| Name | Database |  Upsides | Downsides | Cost | 
| :--- | --- |  --- | --- | --- | 
| [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) | MongoDB |  --- | --- | [Freemium / Pay-as-you-go](https://www.mongodb.com/cloud/atlas/pricing) | 
| [Firebase](https://firebase.google.com/) | Firebase by Google |  --- | --- | [Freemium / Pay-as-you-go](https://firebase.google.com/pricing) | 


## MongoDB Atlas

### What is MongoDB Atlas?

### Setting up MongoDB Atlas

#### Register

* Register an account with [MongoDB Atlas](https://www.mongodb.com/download-center).
  ![Mongodb atlas 00](../assets/mongodb-atlas/mongodb-atlas-00.png)

* Accounts are free / pay-as-you-go
  ![Mongodb atlas 00-1](../assets/mongodb-atlas/mongodb-atlas-00-1.png)

#### Create a new project

* In your admin panel, you will **create a new project**.
  ![Mongodb atlas 01](../assets/mongodb-atlas/mongodb-atlas-01.png)

* Name the project something meaningful.
  ![Mongodb atlas 02](../assets/mongodb-atlas/mongodb-atlas-02.png)

* Confirm: **create project**
  ![Mongodb atlas 03](../assets/mongodb-atlas/mongodb-atlas-03.png)

#### Create a cluster

* In your empty project, you will **build a cluster** - this is referring to a database cluster.
  ![Mongodb atlas 04](../assets/mongodb-atlas/mongodb-atlas-04.png)

* Select the: free **starter clusters** - great for prototyping and testing
  ![Mongodb atlas 05](../assets/mongodb-atlas/mongodb-atlas-05.png)

* Select the cloud provider whose infrastructure your MongoDB server instance will be hosted by. In this case, I chose "google cloud", but AWS and Azure are probably also fine. Also select the **region** - it is recommended that you select the region closest to where you expect your main traffic to be coming from (e.g. if you are in the US, then probably a US based server makes sense).
  ![Mongodb atlas 06](../assets/mongodb-atlas/mongodb-atlas-06.png)

* Name the cluster
  ![Mongodb atlas 07](../assets/mongodb-atlas/mongodb-atlas-07.png)

#### Manage your connections
![Mongodb atlas 08](../assets/mongodb-atlas/mongodb-atlas-08.png)
![Mongodb atlas 09](../assets/mongodb-atlas/mongodb-atlas-09.png)
![Mongodb atlas 10](../assets/mongodb-atlas/mongodb-atlas-10.png)

#### Choosing a connection method

![Mongodb atlas 11](../assets/mongodb-atlas/mongodb-atlas-11.png)
![Mongodb atlas 12](../assets/mongodb-atlas/mongodb-atlas-12.png)



## Firebase:
* Flavio Copes has a great tutorial on this:
  * https://flaviocopes.com/firebase-firestore/
  * https://flaviocopes.com/firebase-hosting/

