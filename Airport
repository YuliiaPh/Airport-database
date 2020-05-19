-- Table: Airline
CREATE TABLE Airline (
    ID_airline integer  NOT NULL,
    name varchar2(20)  NOT NULL,
    CONSTRAINT Linia_lotnicza_ak_1 UNIQUE (name),
    CONSTRAINT Airline_pk PRIMARY KEY (ID_airline)
) ;

-- Table: Bokings
CREATE TABLE Bokings (
    ID_booking integer  NOT NULL,
    ID_passenger integer  NOT NULL,
    ID_flight integer  NOT NULL,
    CONSTRAINT Bokings_pk PRIMARY KEY (ID_booking)
) ;

-- Table: Cities
CREATE TABLE Cities (
    name varchar2(20)  NOT NULL,
    ID_city integer  NOT NULL,
    ID_country integer  NOT NULL,
    CONSTRAINT Cities_pk PRIMARY KEY (ID_city)
) ;

-- Table: Countries
CREATE TABLE Countries (
    ID_country integer  NOT NULL,
    name varchar2(20)  NOT NULL,
    CONSTRAINT Countries_pk PRIMARY KEY (ID_country)
) ;

-- Table: Flights
CREATE TABLE Flights (
    ID_flight integer  NOT NULL,
    departure_time timestamp  NOT NULL,
    arrival_time timestamp  NOT NULL,
    available_seats integer  NOT NULL,
    ID_plane integer  NOT NULL,
    ID_airline integer  NOT NULL,
    ID_destination_city integer  NOT NULL,
    ID_departure_city integer  NOT NULL,
    CONSTRAINT "Check" CHECK (czas_przylot>czas_odlot),
    CONSTRAINT Flights_pk PRIMARY KEY (ID_flight)
) ;

-- Table: Passengers
CREATE TABLE Passengers (
    name varchar2(20)  NOT NULL,
    surname varchar2(20)  NOT NULL,
    ID_passenger integer  NOT NULL,
    birthdate date  NOT NULL,
    CONSTRAINT Passengers_pk PRIMARY KEY (ID_passenger)
) ;

-- Table: Planes
CREATE TABLE Planes (
    name varchar2(20)  NOT NULL,
    ID_plane integer  NOT NULL,
    CONSTRAINT Planes_pk PRIMARY KEY (ID_plane)
) ;

-- foreign keys
-- Reference: Bokings_Flights (table: Bokings)
ALTER TABLE Bokings ADD CONSTRAINT Bokings_Flights
    FOREIGN KEY (ID_flight)
    REFERENCES Flights (ID_flight);

-- Reference: Bokings_Passengers (table: Bokings)
ALTER TABLE Bokings ADD CONSTRAINT Bokings_Passengers
    FOREIGN KEY (ID_passenger)
    REFERENCES Passengers (ID_passenger);

-- Reference: Cities_Countries (table: Cities)
ALTER TABLE Cities ADD CONSTRAINT Cities_Countries
    FOREIGN KEY (ID_country)
    REFERENCES Countries (ID_country);

-- Reference: Flights_Airline (table: Flights)
ALTER TABLE Flights ADD CONSTRAINT Flights_Airline
    FOREIGN KEY (ID_airline)
    REFERENCES Airline (ID_airline);

-- Reference: Flights_Cities (table: Flights)
ALTER TABLE Flights ADD CONSTRAINT Flights_Cities
    FOREIGN KEY (ID_departure_city)
    REFERENCES Cities (ID_city);

-- Reference: Flights_Cities1 (table: Flights)
ALTER TABLE Flights ADD CONSTRAINT Flights_Cities1
    FOREIGN KEY (ID_destination_city)
    REFERENCES Cities (ID_city);

-- Reference: Flights_Planes (table: Flights)
ALTER TABLE Flights ADD CONSTRAINT Flights_Planes
    FOREIGN KEY (ID_plane)
    REFERENCES Planes (ID_plane);

-- End of file.
