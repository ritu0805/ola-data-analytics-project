CREATE TABLE ola_booking (
    date DATE,
    time TIME,
    booking_id VARCHAR(30),
    booking_status VARCHAR(50),
    customer_id VARCHAR(30),
    vehicle_type VARCHAR(50),
    pickup_location VARCHAR(100),
    drop_location VARCHAR(100),
    v_tat NUMERIC,
    c_tat NUMERIC,
    canceled_rides_by_customer TEXT,
    canceled_rides_by_driver TEXT,
    incomplete_rides VARCHAR(20),
    incomplete_rides_reason TEXT,
    booking_value NUMERIC,
    payment_method VARCHAR(50),
    ride_distance NUMERIC,
    driver_ratings NUMERIC,
    customer_rating NUMERIC,
    vehicle_images TEXT
);
select * from ola_booking;


1--Retrieve all successful bookings

SELECT *
FROM ola_booking
WHERE booking_status = 'Success';

2--Find the average ride distance for each vehicle type

SELECT vehicle_type,
    AVG(ride_distance) AS avg_distance
    FROM ola_booking
    GROUP BY vehicle_type;
	
3-- Get the total number of cancelled rides by customers

SELECT COUNT(*) AS total_cancelled_rides
FROM  ola_booking
WHERE canceled_rides_by_customer IS NOT NULL;

4--- Top 5 customers who booked the highest number of rides

SELECT customer_id,COUNT(*) AS total_rides
     FROM ola_booking
    GROUP BY customer_id ORDER BY total_rides DESC LIMIT 5;

5--Rides cancelled by drivers due to personal/car-related issues
SELECT COUNT(*) AS total_cancelled_rides
      FROM  ola_booking
      WHERE canceled_rides_by_driver = 'Personal & Car related issue';


6--Maximum and minimum driver ratings for Prime Sedan

SELECT
    MAX(driver_ratings) AS max_rating,
    MIN(driver_ratings) AS min_rating
FROM ola_booking
WHERE vehicle_type = 'Prime Sedan';

7-- Retrieve all rides where payment was made using UPI

SELECT * FROM ola_booking
WHERE payment_method = 'UPI';

8-- Average customer rating per vehicle type

SELECT vehicle_type,
     AVG(customer_rating) AS avg_customer_rating
     FROM ola_booking
     GROUP BY vehicle_type;	  

9--Total booking value of successfully completed rides

SELECT SUM(booking_value) AS total_successful_value
     FROM ola_booking
     WHERE booking_status = 'Success';

10---List all incomplete rides along with the reason

SELECT booking_id,incomplete_rides_reason
    FROM  ola_booking
    WHERE incomplete_rides = 'Yes';

	  













