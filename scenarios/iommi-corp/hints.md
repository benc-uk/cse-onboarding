# Potential Entity Schemas

A suggestion on the types of entities the system should handle & store, and their structure

```go
// Main customer profile
type Profile struct {
	ID            string
  Account       Account
	GivenName     string
	FamilyName    string
	Age           int
	Address       string
	Picture       Photo
	Subscriptions []Service
}

// Underlying user account
type Account struct {
  ID           string
  EmailAddress string
  UserName     string
}

// Photo data
type Photo struct {
	ProfileID string
	Data      []byte
}

// Service customers can subscribe to
type Service struct {
	ID           string
	Name         string
	MonthlyPrice float64
	Tier         string
}
```

# Potential REST API 

A suggestion of some of the API operations and endpoints, if REST is used

```go
// Get a user's profile
GET   /profile/{id}

// Update a profile
PUT   /profile/{id}

// Update a profile photo
PUT   /profile/{id}/photo/{id}

// Creates a new account and profile
POST  /register      

// Subscribe and unsubscribe to services
PUT      /profile/{id}/subscription/{service_id}
DELETE   /profile/{id}/subscription/{service_id}

// Manage services
GET, POST, PUT, DELETE
      /service

// Manage photos
GET, POST, PUT, DELETE
      /photo
```
