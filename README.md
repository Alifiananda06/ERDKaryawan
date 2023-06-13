# ERDKaryawan


![ca1](https://github.com/Alifiananda06/ERDKaryawan/assets/115884834/dd78e97f-2e25-461b-872e-c499d3c87989)


# Membuat Table

CREATE TABLE departemen (
    -> id_departemen INT PRIMARY KEY,
    -> nama_departemen VARCHAR (50));
    
CREATE TABLE karyawan (
    -> id_karyawan INT PRIMARY KEY,
    -> nama_karyawan VARCHAR (50),
    -> id_departemen INT,
    -> id_manager INT);
    
 CREATE TABLE supervisor(
    -> id_supervisor INT PRIMARY KEY,
    -> id_departemen INT,
    -> id_karyawan INT);
    
CREATE TABLE project(
    -> id_project INT PRIMARY KEY,
    -> nama_project VARCHAR (50),
    -> id_departemen INT);
    
CREATE TABLE karyawan_project(
    -> id_karyawan INT,
    -> id_project INT);
    
  # Menyambungkan Table
  
ALTER TABLE karyawan ADD CONSTRAINT FOREIGN KEY (id_departemen) REFERENCES departemen (id_departemen);
ALTER TABLE supervisor ADD CONSTRAINT FOREIGN KEY (id_departemen) REFERENCES departemen (id_departemen);
ALTER TABLE supervisor ADD CONSTRAINT FOREIGN KEY (id_karyawan) REFERENCES karyawan (id_karyawan);
ALTER TABLE karyawan_project ADD CONSTRAINT FOREIGN KEY (id_karyawan) REFERENCES karyawan (id_karyawan);
ALTER TABLE karyawan ADD CONSTRAINT FOREIGN KEY (id_manager) REFERENCES karyawan (id_karyawan);


Terimakasih:)
