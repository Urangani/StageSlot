#  StageSlot

**Artist Promotion & Booking Platform**

StageSlot is a web-based platform that allows artists to promote their profiles and enables clients to book them transparently. The system shows real-time booking status to prevent double bookings and streamline artist-client coordination.

---

##  Features

### Public

* Browse artists by genre, location, and availability
* View artist profiles (bio, media, rates)
* Public booking calendar with live status
* Clear booking states: **Available / Pending / Booked**

### Clients

* Create and manage booking requests
* View booking history
* Cancel pending bookings
* Real-time booking status updates

### Artists

* Manage artist profile
* Set availability via calendar
* Accept or reject booking requests
* View upcoming and past gigs

### Admin

* Approve and manage artist accounts
* Monitor bookings
* Manage genres and platform data

---

##  Booking Workflow

1. Client selects an artist
2. Chooses date and time
3. System validates availability
4. Booking created with `PENDING` status
5. Artist responds:

   * Accept → `BOOKED`
   * Reject → `REJECTED`
6. Calendar updates instantly

**Booking statuses**

* `AVAILABLE`
* `PENDING`
* `BOOKED`
* `CANCELLED`

---

##  Tech Stack

### Frontend

* React / Next.js
* Tailwind CSS
* FullCalendar

### Backend

* FastAPI (REST API)
* JWT Authentication

### Database

* PostgreSQL (production)
* SQLite (development)

### Hosting

* Frontend: Vercel
* Backend: Railway / Render
* Database: Supabase / Neon

---

##  Project Structure

```
stageslot/
│
├── frontend/
│   ├── pages/
│   ├── components/
│   └── services/
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   └── database.py
│   └── main.py
│
└── README.md
```

---

##  Core Database Models (Simplified)

### User

* id
* name
* email
* role (client, artist, admin)

### Artist

* id
* user_id
* genre
* bio
* rate
* location
* approved

### Booking

* id
* artist_id
* client_id
* date
* start_time
* end_time
* status

### Availability

* id
* artist_id
* date
* start_time
* end_time
* is_available

---

##  Key Design Considerations

* Enforce DB-level constraints to prevent double bookings
* Store all timestamps in UTC
* Validate availability before confirming bookings
* Role-based access control (RBAC)

---

##  Roadmap

### MVP

* Artist profiles
* Booking requests
* Booking status visibility
* Admin approval flow

### Phase 2

* Payments
* Reviews and ratings
* Notifications (email / push)
* Messaging

### Phase 3

* Contracts
* Analytics dashboard
* Agency and team accounts

---

##  Development Setup (Local)

```bash
# Backend
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload

# Frontend
cd frontend
npm install
npm run dev
```

---

## 📄 License

MIT License

---

## 👤 Author
**Uranganu Terrence Mafunzwaini**

---

