# JUMP2DIGITAL
Introducció: 
	Els conjunts de dades utilitzats han estat 2017_lloguer_preu_trim.csv i 2017_poblacio_exposada_barris_mapa_estrategic_soroll_bcn_long.csv.
	Com s'exposa al notebook, el csv base (2017_lloguer_preu_trim.csv), està composat per 8 columnes que representen principalment la localització
	de l'habitatge (barri i districte), la data (any), i el preu del lloguer (total o en metres quadrats).
	D'altra banda, el conjunt de dades 2017_poblacio_exposada_barris_mapa_estrategic_soroll_bcn_long.csv, identifica la localització (barri i discricte),
	el concepte, el rang de soroll de decibels, i el valor corresponent al rang de decibels (en percentatge).
	El concepte està codificat de la següent manera (informació obtinguda de https://ajuntament.barcelona.cat/ecologiaurbana/es/mapas-datos-ambientales):
		TOTAL --> Soroll total
		TRANSIT --> Soroll de trànsit viari
		GI_TR --> Soroll de grans infraestructures viàries
		FFCC --> Soroll d'eixos ferroviaris i tramvia
		INDUST --> Soroll d'indústria
		VIANANTS --> Soroll de trànsit viari
		OCI --> Soroll d'oci i aglomeració de persones
		PATIS --> Soroll en patis interior d'illa
		PARCS -- Soroll en parcs
		D --> Dia 7 a 21h
		E --> Vespre 21 a 23h
		N --> Nit 23 a 7h

Depuració de dades:
	El preprocessament de les dades està composat per: evaluació dels valors absents, eliminació de columnes redundants, codificació de columnes nominals/intervals, 
	i estandarització de les columnes.
	La evaluació de valors absents es descomposa en una observació inicial dels valors absents a la columna 'Preu', i un estudi posterior de l'aleatoritat d'aquesta 
	absència. Es conclou que no és negligibe la absència d'aquests valors, i que hi ha alguns barris en els quals no hi ha cap registre del preu de l'habitatge.
	L'eliminació de columnes redundants es basa en evaluar la codificació dels barris i districtes, per arribar a la conclusió que la informació que aporta el codi no és significativa, ja que els números no segueixen un ordre 
  d'interès. La codificació de les columnes nominals/intervals es basa en portar a terme un one-hot encoding pels atributs nominals, i utilitzar label encoding pels intervals. Cal remarcar que és possible utilitzar    el 
  label encoding ja que els intervals tenen un ordre intrínsec, i per tant poden ser numerats. 
  La estandarització de les columnes facilita l'anlàsi posterior dels components principals, ja que el PCA és sensible a les variables amb diferent escala.
  
Resultats i Conclusions:
  Després de portar a terme l'anàlisi de les components principals, concluim que amb un total de 86 dimensions podem conservar un 90% de la variança acumulada. Cal remarcar que la gran quantitat de barris
	i la seva codificació és un factor a tenir en compte al avaluar els resultats, ja que l'augment de la dimensionalitat augmenta la complexitat del conjunt de dades, i l'estudi d'aquest es torna més díficil.
  
  
