# Codigo clases practicas de la universidad
```sql
--Crear tablas
  CREATE TABLE llamada(
    tf_origen char(9),
    tf_destino char(9),
    fecha_hora timestamp,
    duracion number(5,0),
    CONSTRAINT llamada_pk PRIMARY KEY(tf_origen, fecha_hora),
    CONSTRAINT llamada_fk
    FOREIGN KEY(tf_origen) REFERENCES TELEFONO(numero),
    CONSTRAINT llmada2
    FOREIGN KEY(tf_destino) REFERENCES TELEFONO(numero),
    CONSTRAINT llamada_unica UNIQUE (tf_destino, fecha_hora));

--modificar tablas
  ALTER TABLE TARIFA
  DROP CONSTRAINT COMPAÑIA_FK;
  
  ALTER TABLE TARIFA
  ADD CONSTRAINT COMPAÑIA_FK FOREIGN KEY(COMPAÑIA) references COMPAÑIA(CIF) ON DELETE CASCADE;

  --Insertar en tablas

  INSERT INTO COMPAÑIA 
VALUES('A00000001', 'Kietostar', 'http://www.kietostar.com');

INSERT INTO COMPAÑIA
VALUES('B00000002','Aotra','http://www.aotra.com');

INSERT INTO TARIFA
VALUES('familiar','A00000001','la pareja también está en la compañía',0.15);

INSERT INTO TARIFA
VALUES('autónomos','B00000002','trabajador autónomo',0.12);

INSERT INTO TARIFA
VALUES('dúo','B00000002','la pareja también está en la compañía',0.15);

INSERT INTO COMPAÑIA
VALUES('A00000001','Petafón','http://www.petafón.com '); --No funciona porque se incumple   que el ID ya existe

``` 
