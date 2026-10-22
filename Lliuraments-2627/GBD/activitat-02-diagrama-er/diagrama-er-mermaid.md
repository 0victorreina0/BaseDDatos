# Diagrama ER - Mermaid

A continuació tens un exemple bàsic de diagrama ER en Mermaid que pots adaptar a l'activitat.

```mermaid
erDiagram
    CLIENT ||--o{ COMANDA : realitza
    EMPLEAT ||--o{ COMANDA : atén
    COMANDA ||--|{ LINIA_COMANDA : inclou
    PRODUCTE ||--o{ LINIA_COMANDA : apareix

    CLIENT {
        int id_client PK
        string nom
        string email
        string telefon
    }

    EMPLEAT {
        int id_empleat PK
        string nom
        string cognoms
        string rol
    }

    COMANDA {
        int id_comanda PK
        date data_comanda
        float total
        int id_client FK
        int id_empleat FK
    }

    PRODUCTE {
        int id_producte PK
        string nom
        string categoria
        decimal preu
    }

    LINIA_COMANDA {
        int id_linia PK
        int quantitat
        decimal subtotal
        int id_comanda FK
        int id_producte FK
    }
```

Aquest model representa una relació típica entre clients, empleats, comandes i productes.
