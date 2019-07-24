1. Let's start by figuring out how many dinosaurs we have. Count the number of dinosaurs.
dinosaurs=# SELECT COUNT(id) FROM dinos;
 count 
-------
   331
(1 row)

2. Find all the dinosaurs from the Jurassic period.
SELECT name FROM dinos;
          name           
-------------------------
 Wuerhosaurus
 Velociraptor
 Yuanmousaurus
 Yinlong
 Yingshanosaurus
 Yimenosaurus
 Yangchuanosaurus
 Yandusaurus
 Vulcanodon
 Valdosaurus
 Tuojiangosaurus
 Utahraptor
 Urbacodon
 Unenlagia
 Tyrannosaurus
 Tylocephale
 Tsagantegia
 Troodon
 Triceratops
 Torvosaurus
 Torosaurus
 Thescelosaurus
 Zephyrosaurus
 Yunnanosaurus
 Zalmoxes
 Udanoceratops
 Syntarsus
 Telmatosaurus
 Tarchia
 Tarbosaurus
 Tanius
 Talarurus
 Panoplosaurus
 Supersaurus
 Staurikosaurus
 Suchomimus
 Styracosaurus
 Stygimoloch
 Struthiosaurus
 Struthiomimus
 Stenopelix
 Spinosaurus
 Sinraptor
 Sonidosaurus
 Stegosaurus
 Sinvenator
 Sinosauropteryx
 Sinornithosaurus
 Tenontosaurus
 Sinocalliopteryx
 Thecodontosaurus
 Stegoceras
 Silvisaurus
 Seismosaurus
 Shanag
 Segnosaurus
 Secernosaurus
 Segisaurus
 Saurornithoides
 Scutellosaurus
 Sauropelta
 Scelidosaurus
 Saurophaganax
 Saurolophus
 Sarcosaurus
 Saltasaurus
 Saichania
 Shantungosaurus


3. Find the total sum length of all the dinosaurs from the Cretaceous period.
dinosaurs=# SELECT SUM(length) FROM dinos WHERE period = 'Cretaceous';
   sum   
---------
 1366.45
(1 row)

4. Find all the dinosaurs from either the Jurassic OR Cretaceous periods, and order them by their species name alphabetically.

SELECT name  FROM dinos WHERE period = 'Jurassic' OR  period = 'Cretaceous' ORDER BY name ASC;
          name           
-------------------------
 Aardonyx
 Abelisaurus
 Achelousaurus
 Achillobator
 Acrocanthosaurus
 Aegyptosaurus
 Afrovenator
 Agilisaurus
 Alamosaurus
 Albertaceratops
 Albertosaurus
 Alectrosaurus
 Alioramus
 Allosaurus
 Alvarezsaurus
 Amargasaurus
 Ammosaurus
 Ampelosaurus
 Amygdalodon
 Anatotitan
 Anchiceratops
 Anchisaurus
 Ankylosaurus
 Anserimimus
 Antarctopelta
 Antarctosaurus
 Apatosaurus
 Aragosaurus
 Aralosaurus
 Archaeoceratops
 Archaeopteryx
 Archaeornithomimus
 Argentinosaurus
 Arrhinoceratops
 Atlascopcosaurus
 Aucasaurus
 Austrosaurus
 Avaceratops
 Avimimus
 Bactrosaurus
 Bagaceratops
 Bambiraptor
 Barapasaurus
 Barosaurus
 Baryonyx
 Becklespinax
 Beipiaosaurus
 Bellusaurus
 Borogovia
 Brachiosaurus
 Brachyceratops
 Brachylophosaurus
 Brachytrachelopan
 Bugenasaura
 Buitreraptor
 Camarasaurus
 Camptosaurus
 Carcharodontosaurus
 Carnotaurus
 Caudipteryx
 Cedarpelta
 Centrosaurus
 Ceratosaurus
 Cetiosauriscus
 Cetiosaurus
 Chaoyangsaurus
 Chasmosaurus
  etc...
  
  5. Find all the dinosaurs from the t_order Saurischia that are Herbivorous.
  SELECT name FROM dinos WHERE t_order = 'Saurischia' AND diet = 'Herbivorous';
        name         
---------------------
 Yuanmousaurus
 Yimenosaurus
 Vulcanodon
 Supersaurus
 Sonidosaurus
 Seismosaurus
 Saltasaurus
 Rebbachisaurus
 etc...
(68 rows)

6. Find the shortest dinosaur, and rename it Shortie.

dinosaurs=# SELECT MIN(length) FROM dinos;
 min  
------
 0.08
(1 row)
dinosaurs=# SELECT name FROM dinos WHERE length =  0.08;
    name     
-------------
 Liaoxiornis
(1 row)

dinosaurs=# UPDATE dinos SET name = 'Shortie' WHERE length = 0.08;
UPDATE 1
dinosaurs=# SELECT name FROM dinos WHERE length =  0.08;
  name   
---------
 Shortie
(1 row)

7. Find the alphabetically first dinosaur, so we can make sure they're present for class.
dinosaurs=# SELECT name FROM dinos ORDER BY name ASC FETCH first row only;
   name   
----------
 Aardonyx
(1 row)

dinosaurs=#
