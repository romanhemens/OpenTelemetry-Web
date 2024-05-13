#  Auto-Instrument Petclinic

The project includes the automatic instrumentation of the backend (which can be found [here](https://github.com/spring-petclinic/spring-petclinic-rest/blob/master)) with InspectIT Ocelot. Additionally, the frontend written in Angular (Repo can be found [here](ttps://github.com/spring-petclinic/spring-petclinic-angular/blob/master)) is instrumented with OpenTelemetry. The recorded traces are sent to [ExplorViz](https://github.com/ExplorViz), which can visualize them.

## Table of Contents

- [Auto-Instrument-JavaScript-NodeJS](#Auto-Instrument-JavaScript-NodeJS)
  - [Table of Contents](#table-of-contents)
  - [About the Project](#about-the-project)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [License](#license)

## About the Project

This project enhances the sample of examples of how to use OpenTelemetry to automatically instrument signals from JavaScript software. Therefore, a complete application with an Angular frontend and Java backend is utilized. Both's data is exported to ExplorViz, where both are visualized together as a software landscape. While the Angular project is completely embedded into this project, the Java backend is build only via a Dockerfile, which uses the public github repository.

## Getting Started

Instructions for setting up the project on a local machine.

### Prerequisites

The user needs to have both Docker and Docker compose installed.

You could install an additional exporter like Zipkin, to send the instrumented traces to the respective backend, however this repository is made to visualize them in ExplorViz.

To do that, please clone into the [Deployment](https://github.com/ExplorViz/deployment) and the [Frontend](https://github.com/ExplorViz/frontend) and follow their instructions to get ExplorViz running. 

### Installation

Without the utilization of Explorviz just use the following command to build and run the example:

    docker-compose up --build -d

With the utilization of ExplorViz, you need to create an .env-custom, which mirrors the .env file, but you insert your values for the token and its secret of your created landscape in ExplorViz. Make sure that the network of your ExplorViz's container is the same as the ones in this docker-compose file. The following command builds and runs the example:

    docker-compose --env-file .env-custom up --build -d

If you plan to stop everything and delete the created volumes, use this command:

    docker-compose down -v or docker-compose --env-file .env-custom down -v

## License

License can be found [here](/LICENSE)


