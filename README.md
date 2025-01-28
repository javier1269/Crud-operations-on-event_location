CREATE TABLE event_locations (
    event_id SERIAL PRIMARY KEY, -- Unique ID for each location
    event_name VARCHAR(255) NOT NULL, -- Name of the event
    country VARCHAR(100) NOT NULL, -- Country of the event
    state VARCHAR(100), -- State (optional)
    city VARCHAR(100), -- City
    latitude NUMERIC(9, 6) NOT NULL, -- Latitude (e.g., 37.7749)
    longitude NUMERIC(9, 6) NOT NULL, -- Longitude (e.g., -122.4194)
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP -- Timestamp for when the record was created
);

INSERT INTO event_locations (event_id,event_name, country, state, city, latitude, longitude)
VALUES (5,'Cyclone Help 2025', 'India', 'Odisha', 'Bhubaneswar', 20.2961, 85.8245);

SELECT * 
FROM event_locations
WHERE event_name = 'Flood Relief 2025';

UPDATE event_locations
SET city = 'Los Angeles',
    latitude = 34.0522,
    longitude = -118.2437
WHERE event_name = 'Flood Relief 2025';

DELETE FROM event_locations
WHERE event_name = 'Flood Relief 2025';

SELECT * FROM public.event_locations
ORDER BY event_id ASC 
