```mermaid
sequenceDiagram
    loop periodicamente
        alt without PDND
            ANS-->>ANIS: invia i tracciati
            ANIS-->>ANS: carica studenti e iscrizioni
        else with PDND
            ANIS-->>IFS: Elenco variazioni iscrizioni

            ANIS-->>IFS: Elenco variazioni titoli
        end
    end
    loop ogni anno accademico
        ANIS-->>ANS: richiede vocabolari controllati
        ANS-->>ANIS: vocabolari controllati
        ANIS-->>ANIS: carica i vocabolari controllati
    end
```