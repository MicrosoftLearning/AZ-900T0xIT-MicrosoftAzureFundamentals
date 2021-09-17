---
wts:
    title: '20 - Usare il Calcolatore del costo totale di proprietà di Azure (10 min)'
    module: 'Modulo 06: Descrizione di Gestione costi di Azure e Contratti di servizio'
---
# 20. Usare il Calcolatore del costo totale di proprietà di Azure (10 min)


In questa procedura dettagliata verrà usato il Calcolatore del costo totale di proprietà (TCO) per generare un report di confronto sui costi per un ambiente locale.

**Nota**: questa procedura dettagliata include definizioni di esempio di un'infrastruttura locale e dei carichi di lavoro per una tipico data center. Per creare un report del calcolatore del costo totale di proprietà, usare le definizioni di esempio oppure fornire i dettagli dell'infrastruttura locale e dei carichi di lavoro *effettivi*.

# Attività 1. Configurare il Calcolatore del costo totale di proprietà (TCO)

In questa attività verranno aggiunte informazioni sull'infrastruttura nel calcolatore. 

1. In un browser passare alla pagina [Calcolatore del costo totale di proprietà](https://azure.microsoft.com/it-it/pricing/tco/calculator/).

2. Per aggiungere i dettagli dell'infrastruttura server locale, fare clic su **+ Aggiungi il carico di lavoro del server** nel riquadro **Definisci i tuoi carichi di lavoro**.

    | Impostazioni | Valore |
    | -- | -- |
    | Nome | **Server: Windows VMs** |
    | Carico di lavoro | **Server Windows/Linux** |
    | Ambiente | **Macchine virtuali** |
    | Sistema operativo | **Windows** |  
    | Macchine virtuali | **50** |
    | Virtualizzazione | **Hyper-V** |
    | Core | **8**|
    | RAM (GB) | **16** |
    | Ottimizza in base a | **CPU** |
    | Windows Server 2008/2008 R2 | **No** |

3. Selezionare **+ Aggiungi il carico di lavoro del server** per creare una riga per una nuova definizione di carichi di lavoro del server. 

    | Impostazioni | Valore |
    | -- | -- |
    | Nome | **Server: Linux VMs** |
    | Carico di lavoro | **Server Windows/Linux** |
    | Ambiente | **Macchine virtuali** |
    | Sistema operativo | **Linux** |  
    | Macchine virtuali | **50** |
    | Virtualizzazione | **VMware** |
    | Core | **8**|
    | RAM (GB) | **16** |
    | Ottimizza in base a | **CPU** |
    | Windows Server 2008/2008 R2 | **No** |

4. Nel riquadro **Archiviazione** fare clic su **Aggiungi le risorse di archiviazione**.

    | Impostazioni | Valore |
    | -- | -- |
    | Nome | **Archiviazione server** |
    | Tipo di risorse di archiviazione | **Disco locale/SAN** |
    | Tipo di disco | **Unità disco rigido** |
    | Capacità | **60 TB** |  
    | Backup | **120 TB** |
    | Archivio | **0 TB** |

5. Nel riquadro **Rete** aggiungere larghezza di banda. 

    | Impostazioni | Valore |
    | -- | -- |
    | Larghezza di banda in uscita | 15 TB|

6. Fare clic su **Successivi**.

7. Esplorare le opzioni e apportare le eventuali modifiche necessarie. 

    | Impostazioni | Valore |
    | -- | -- |
    | Valuta | **Euro** |

8. Fare clic su **Successivi**.

# Attività 2. Esaminare i risultati e salvare una copia

In questa attività verranno esaminate le raccomandazioni per il risparmio sui costi e verrà scaricato un report. 

1. Esaminare le raccomandazioni e le visualizzazioni per il risparmio sui costi.

    | Impostazioni | Valore |
    | -- | -- |
    | Intervallo di tempo| **3 anni** |
    | Area | **Europa settentrionale** |

2. Per modificare le informazioni specificate, passare alla fine della pagina e fare clic su **Indietro**. 

3. Per salvare o stampare una copia in formato PDF del report, fare clic su **Scarica**.

    ![Screenshot del riquadro del report del Calcolatore del costo totale di proprietà in Azure. I campi di input evidenziati e completati indicano come impostare l'intervallo di tempo del Calcolatore del costo totale di proprietà su tre anni e l'area su Europa settentrionale. Un grafo mostra la differenza tra il costo dell'infrastruttura locale e dei carichi di lavoro e il costo ridotto usando Azure.](../images/2001.png)

Congratulazioni! È stato usato il Calcolatore del costo totale di proprietà per generare un report di confronto dei costi per un ambiente locale.
