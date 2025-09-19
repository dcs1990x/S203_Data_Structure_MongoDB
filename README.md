# Sprint 2, Task 3: Database Structure - MySQL

This repository contains MongoDB database designs for an optical store management system, focusing on different perspectives and requirements for product, customer, and sales tracking.

## 📁 Project Structure

The project implements MongoDB database designs for an optical store called "Cul d'Ampolla" with two different perspectives:

- **Customer-centric view**: Database design optimized for customer interactions
- **Product-centric view**: Database design optimized for glasses inventory management

## 💻 Technologies

- **MongoDB 5.0+**
- **MongoDB Compass** (Recommended for visualization)
- **NoSQL document-based structure**

## 📋 Database Design

### 🕶️ Optical Store "Cul d'Ampolla"

#### Core Collection Structure

**Customer**

```javascript
{
  _id: ObjectId,
  name: String,
  surname: String,
  address: {
    street: String,
    number: Number,
    floor: Number,
    door: Number,
    municipality: String,
    postal_code: String,
    country: String
  },
  referred_by: Object,
  registration_date: ISODate,
  last_sale: {
   glasses: Object,
   sold_by: {
      name: String,
      surname: String
   }
   sate_date: ISODate
}
```

**Glasses**

```javascript
{
  brand: String,
  measurement: {
    left: Decimal,     
    right: Decimal    
  },
  frame_type: String,  
  frame_colour: String,
  glass_colour: {
    left: String,
    right: String
  },
  price: Double,
  supplier: Object
}
```

**Supplier**

```javascript
{
  name: String,
  address: {
    street: String,
    number: Number,
    floor: Number,
    door: Number,
    municipality: String,
    postal_code: String,
    country: String
  },
  phone: String,
  fax: String,
  tax_id: String
}
```

## 🚀 How to Implement   

- Clone the repository
- Open MongoDB Shell or Compass
- Import the opticiandb.optician_client.json and opticiandb.optician_glasses.json datasets into your MongoDB instance

## 📊 Performance Considerations   

- Indexes: Create indexes on frequently queried fields
- Sharding: Plan for horizontal scaling based on access patterns
- Storage: Consider storage engine options based on read/write patterns
- Backup: Implement regular backup strategies for business continuity

## 👨‍💻 Author   
Developed by Daniel Caldito Serrano as part of the Java Back-end Development Bootcamp at the IT Academy.
