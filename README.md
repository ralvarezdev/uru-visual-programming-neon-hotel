# uru-visual-programming-neon-hotel

**Note:** Archived and read-only. Kept for reference from the Visual Programming college course.

A simple Windows GUI application ("Neon Hotel") built with C++Builder (VCL framework), for the Visual Programming college course. It manages hotel events, guest types and guest registrations against a PostgreSQL database, behind a login screen with role-based access (admin).

## Tech stack

- **C++Builder** project (`NeonHotel.cbproj`, VCL `Application`/`Win32` target)
- **PostgreSQL**, accessed through VCL data-aware components (`TQuery`/dataset params) bound to `.dfm` forms

## Units

- **`MainUnit`** — login form; validates credentials against the `Users` table and routes admins to the events screen.
- **`EventsUnit`** — lists/manages hotel events.
- **`EventTypesUnit`** — manages the event type catalog.
- **`EventGuestsUnit`** / **`EventGuestAttendeesUnit`** — manage guests and attendee details for an event.
- **`GuestTypesUnit`** — manages the guest type catalog.

Each unit has a `.cpp`/`.h`/`.dfm` triple (VCL form + generated code + implementation).

## Database schema

`model/` contains the PostgreSQL DDL and seed data, applied in order: `create-enums.sql`, `create-tables.sql` (`Events`, `Event_Types`, `Users`, `Guest_Types`, and related guest/attendee tables), `add-constraints.sql`, then the `insert*.sql` seed files.

## Running

Requires **Embarcadero C++Builder** (or RAD Studio) to open `NeonHotel.cbproj` and build for Win32, plus a PostgreSQL instance with the schema from `model/` applied and the VCL data connection components configured to point at it.

## License

GNU General Public License v3.0 (see `LICENSE.txt`).
