# NeighborConnect Backend Repository

## Overview
This package repository contains database interaction functions for managing users, accounts, apartments, managers, transactions, listings, and events in the NeighborConnect backend system. The repository interfaces with a PostgreSQL database using `pgxpool`.

## Table of Contents
- [Installation](#installation)
- [Database Models](#database-models)
- [Repository Functions](#repository-functions)
  - [User Management](#user-management)
  - [Manager Management](#manager-management)
  - [Apartment Management](#apartment-management)
  - [Account Management](#account-management)
  - [Withdrawals](#withdrawals)
  - [Listings & Transactions](#listings--transactions)
  - [Community Events](#community-events)

## Installation
To use this package, install the required Go dependencies:
```sh
 go get github.com/jackc/pgx/v5/pgxpool
```
Ensure that you have a running PostgreSQL database instance and update your connection settings accordingly.

## Database Models
This package defines the following models:

- **Account**: Stores user account details.
- **Apartment**: Stores apartment details.
- **Manager**: Represents property managers.
- **User**: Stores user information.
- **Withdraw**: Handles withdrawal transactions.
- **Transaction**: Stores transaction details.
- **Listing**: Represents auction listings.
- **Item**: Stores item details for listings.
- **Bid**: Stores bid data.
- **Community_Event**: Represents community events.

## Repository Functions

### User Management
#### Create a User
```go
func CreateUser(user models.User, dbPool *pgxpool.Pool) error
```
Inserts a new user into the `users` table.

#### Get User by Email
```go
func GetUserByEmail(email string, dbPool *pgxpool.Pool) (models.User, error)
```
Retrieves a user by their email.

### Manager Management
#### Create a Manager
```go
func CreateManager(manager models.Manager, dbPool *pgxpool.Pool) error
```
Inserts a new manager into the `manager` table.

#### Get Manager by Email
```go
func GetManagerByEmail(email string, dbPool *pgxpool.Pool) (models.Manager, error)
```
Retrieves a manager by their email.

### Apartment Management
#### Create an Apartment
```go
func CreateApartment(apartment models.Apartment, db *pgxpool.Pool) error
```
Inserts a new apartment into the `apartment` table.

### Account Management
#### Create an Account
```go
func CreateAccount(account models.Account, dbPool *pgxpool.Pool) error
```
Creates a new user account.

### Withdrawals
#### Create a Withdrawal
```go
func CreateWithdraw(withdraw models.Withdraw, dbPool *pgxpool.Pool) error
```
Handles withdrawal transactions.

### Listings & Transactions
These models facilitate online transactions and auctions.

- **Listings**: Auctions for items.
- **Bids**: Users can place bids on listings.
- **Transactions**: Finalized purchase details.

### Community Events
Manages community events including capacity, date, and manager.
