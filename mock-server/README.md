# Residence Harmonie Mock Servers

This directory contains the configuration and dummy data for running a local mock backend for the Residence Management System.

## Prerequisites
- Node.js (v14 or higher)
- npm

## Installation
Run the following command to install the required development dependencies (Prism CLI and JSON Server):
```bash
npm install
```

## Running the Servers

### Option 1: Prism (OpenAPI Mocking)
Prism uses the `openapi.yaml` specification to generate a robust mock server. It automatically validates incoming requests and returns dummy responses based on the schemas defined in the spec.

**Start Prism:**
```bash
npm run mock:prism
```
*The server will run on `http://localhost:4010`.*

### Option 2: JSON Server (Fake REST API)
JSON Server provides a full fake REST API using the `db.json` file as its database. It allows you to perform actual CRUD operations (GET, POST, PUT, PATCH, DELETE) and persists data in memory/file during execution. This is ideal for frontend development that requires stateful data (like marking tasks as done).

**Start JSON Server:**
```bash
npm run mock:json-server
```
*The server will run on `http://localhost:3001`.*

## Data Structure
The `db.json` contains realistic demo data spanning two different tenants (Residences) to demonstrate multi-tenancy (`residenceId: "residence-1"` and `"residence-2"`). The data includes:
- Administrative catalogs (Rooms, Shifts, Periods, Task Catalog)
- Employee Tasks and Residents (e.g., Jean Dupuis)
- Dashboard statistics and reports
