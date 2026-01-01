# Étude de Cas : Clients Synchrones - RestTemplate vs Feign vs WebClient

Comparaison des différents clients HTTP synchrones Spring avec intégration Eureka et Consul pour la découverte de services.

## Technologies

- **Spring Boot 3.x**
- **Spring Cloud**
- **Eureka Server**
- **Consul**
- **RestTemplate**
- **OpenFeign**
- **WebClient**

## Architecture

Le projet contient plusieurs microservices :

- **discovery-service** - Serveur Eureka pour la découverte de services
- **service-voiture** - Service de gestion des voitures
- **service-client** - Service de gestion des clients

## Clients HTTP Comparés

### 1. RestTemplate (Traditionnel)
Client HTTP synchrone classique de Spring.

### 2. OpenFeign (Déclaratif)
Client HTTP déclaratif avec annotations.

### 3. WebClient (Réactif)
Client HTTP moderne, supporte les appels synchrones et asynchrones.

## Démarrage

### 1. Démarrer Eureka Discovery Service

```bash
cd discovery-service
mvn spring-boot:run
```

Accès : `http://localhost:8761`

### 2. Démarrer les Microservices

```bash
cd service-voiture
mvn spring-boot:run
```

```bash
cd service-client
mvn spring-boot:run
```

## Endpoints

### Service Voiture

- `GET /voitures` - Liste des voitures
- `GET /voitures/{id}` - Détails d'une voiture
- `POST /voitures` - Créer une voiture
- `PUT /voitures/{id}` - Mettre à jour une voiture
- `DELETE /voitures/{id}` - Supprimer une voiture

### Service Client

- `GET /clients` - Liste des clients
- `GET /clients/{id}` - Détails d'un client avec ses voitures

## Découverte de Services

Le projet utilise **Eureka** pour la découverte automatique des services.

Configuration Consul disponible en alternative.

## Comparaison des Clients

| Client | Type | Avantages | Inconvénients |
|--------|------|-----------|---------------|
| RestTemplate | Synchrone | Simple, bien connu | Obsolète, verbeux |
| Feign | Synchrone | Déclaratif, élégant | Configuration limitée |
| WebClient | Sync/Async | Moderne, flexible | Courbe d'apprentissage |

## Auteur

**Yassine Radim**
# Etude-de-cas-Clients-Synchrones-RestTemplate-vs-Feign-vs-WebClient-avec-Eureka-et-Consul-main
