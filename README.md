# DataBase_Sql
This is a project to create a database for managing a cinema chain called CINETICKET.
This README is a small description for more details consult the file "project report".

GENERAL INFORMATION:

This project is aimed at the creation of a database that allows the management and 
planning shows within a cinema chain. The human resources of the cinema are 
formed by users and operators, who direct the activities and deal with the "economic" part.
A database that manages a cinema chain allows you to view shows
movie, to be able to buy loyalty cards that subsequently allow users 
to own discounts, buy tickets and choose the type of rooms. Next 
we will explain how this specific database will be implemented step by step, introducing all 
the minimum requirements specified in the prototype design.

ANALYSIS OF REQUIREMENTS
The CINETICKET database manages the bookings for the shows of a cinema chain to which the 
users can assist, the final goal of the project is a correct and consistent conservation of 
all processed data that will be subsequently deepened. 
In the database, each user has the possibility to insert one or more tickets in his shopping cart, 
each ticket is associated with a show that in turn is associated with a cinema identified by 
a compound natural key based on its geographical location. The ticket is also connected
a room and a place. The user after purchasing the ticket can insert a review 
giving one vote for each category of the film.
Of the latter we know the production company that made it and who participated,
both as an actor and as a director.The cinema chain allows the user to own a loyalty card that allows in turn to 
to receive promotions applied on shopping carts. Each cinema has various halls of different types 
connected to the various shows in the program. The user can independently "carry out some 
purchases" by changing the payment date of your cart, tickets linked to shows 
finished and never purchased are automatically deleted.
Similarly the user can cancel an order and have a "refund" if the cancellation is 
requested at least one day before the date of the nearest show.
In our project we also recognize another figure who can actively interact with the database, 
or the operator.The latter can manage the structure of the various cinemas by entering the data concerning the shows, the 
salt and places.
The operator also has the task of verifying that the various users perform the operations correctly 
to insert reviews and change the qualification to its future purchases.

The requirements analysis then produces a database of the following entities:
- Utente (Attributi: Username, Nome, Cognome, Sesso, Data_di_nascita, Luogo_di_nascita, Abilitato)
- Carta Fedeltà (Attributi: Codice carta fedeltà, Data scadenza)
- Promozione (Attributi: Codice promozione, Nome promozione, Data inizio promozione, Data fine promozione)
- Carrello (Attributi: Codice carrello, Data pagamento)
- Carta di credito (Attributi: Numero carta, Codice CVV, Data Scadenza)
- Biglietto (Attributi: Codice biglietto, prezzo)
- Recensione (Attributi: Id recensione, Voto: Voto Protagonista, Voto Antagonista, Voto Trama, Voto Sceneggiatura, Voto Colonna Sonora)
- Posto (Attributi: Nome Posto: Fila Posto, Numero Posto)
- Sala (Attributi: Codice Sala, Tipo sala, Numero sala, Massima capienza)
- Cinema (Attributi: Indirizzo cinema: Via ,Città, CAP; Nome cinema)
- Spettacolo (Attributi: Data spettacolo: Ora inizio, Ora fine; Lingua)
- Film (Attributi: Codice film, Trama, Genere, Classificazione, Anno produzione, Durata, Titolo)
- Compagnia di produzione (Attributi: Nome compagnia, Città)
- Professionista (Codice professionista, Nome, Data di nascita)
  
The link between the various entities is made through the following associations/relationships:
- The user renews the loyalty card (Association attributes: Subscription date)
- The loyalty card Offers promotion
- The promotion Is applied on the cart
- Payment cart with credit card
- Cart has a ticket
- User enters in Cart (Association attributes: Date entered)
- Associated ticket Seat
- Room contains Place
- Cinema consists of Sala
- Ticket Writes Review (Association Attributes: Publication Date)
- Ticket From Entry to Performance
- Show Screened in the Hall
- Review about Film
- Show includes Film
- Film produced by production company
- Film Directed by Director (Director Entity daughter of Professional)
- Actor Acting Film (Professional Child Actor, Association Attributes: Role Name)


