---
wts:
    title: '12 - Implementare Azure Key Vault (5 min)'
    module: 'Modulo 04: Descrizione delle funzionalità di sicurezza generali e di rete'
---
# 12 - Implementare Azure Key Vault

In questa procedura dettagliata verrà creata un'istanza di Azure Key Vault al cui interno verrà creato un segreto che rende disponibile una password gestita centralmente e archiviata in modo sicuro da usare con le applicazioni.

# Attività 1. Creare un'istanza di Azure Key Vault (5 min)

1. Accedere al [portale di Azure](https://portal.azure.com).

2. Nel pannello **Tutti i servizi** cercare e selezionare **Insiemi di credenziali delle chiavi**, quindi fare clic su **+ Aggiungi, + Crea oppure + Nuovo**.

3. Configurare l'insieme di credenziali delle chiavi (sostituire **xxxx** con lettere e numeri in modo che il nome sia univoco a livello globale). Lasciare i valori predefiniti per tutto il resto.

    | Impostazione | Valore | 
    | --- | --- |
    | Sottoscrizione | **Usare la propria sottoscrizione** |
    | Gruppo di risorse | **myRGKV** (Crea nuovo) |
    | Nome insieme di credenziali delle chiavi | **keyvaulttestxxx** |
    | Località | **Stati Uniti orientali** |
    | Piano tariffario | **Standard** |
    | | |

4. Fare clic su **Rivedi e crea** e, dopo la convalida, su **Crea**. 

5. Una volta completato il provisioning del nuovo insieme di credenziali delle chiavi, fare clic su **Vai alla risorsa**. In alternativa, è possibile individuare il nuovo insieme di credenziali delle chiavi tramite ricerca. 

6. Fare clic sulla scheda **Panoramica** dell'insieme di credenziali delle chiavi e prendere nota del valore di **Nome DNS**. Questo URI sarà necessario per le applicazioni che usano l'insieme di credenziali tramite l'API REST.

7. Esplorare alcune delle altre opzioni dell'insieme di credenziali delle chiavi. In **Impostazioni** esaminare le opzioni **Chiavi**, **Segreti**, **Certificati**, **Criteri di accesso**, **Firewall e reti virtuali**.

    **Nota**: l'account Azure è l'unico autorizzato a eseguire operazioni in questo nuovo insieme di credenziali. È possibile modificare le autorizzazioni nella sezione **Criteri di accesso** in **Impostazioni**.

# Attività 2. Aggiungere un segreto all'insieme di credenziali delle chiavi
        
In questa attività verrà aggiunta una password all'insieme di credenziali delle chiavi. 

1. In **Impostazioni** fare clic su **Segreti** e quindi su **+ Genera/Importa**.

2. Configurare il segreto. Lasciare i valori predefiniti per le altre impostazioni. È possibile impostare una data di attivazione e una data di scadenza. È anche possibile disabilitare il segreto.

    | Impostazione | Valore | 
    | --- | --- |
    | Opzioni di caricamento | **Manuale** |
    | Nome | **ExamplePassword** |
    | Valore | **hVFkk96** |
    | | |

3. Fare clic su **Crea**.

4. Dopo aver creato il segreto, fare clic su **ExamplePassword** e notare che lo stato è **Abilitato**

5. Fare clic sulla versione corrente e prendere nota del valore di **Identificatore del segreto**. Questo è il valore dell'URL che è ora possibile usare con le applicazioni. Rende disponibile una password gestita centralmente e archiviata in modo sicuro.

6. Fare clic sul pulsante **Mostra il valore segreto** per visualizzare la password specificata in precedenza.

Congratulazioni! È stata creata un'istanza di Azure Key Vault al cui interno è stato creato un segreto che rende disponibile una password gestita centralmente e archiviata in modo sicuro da usare con le applicazioni.

**Nota**: per evitare costi aggiuntivi, è possibile rimuovere questo gruppo di risorse. Cercare e selezionare il gruppo di risorse, quindi fare clic su **Elimina gruppo di risorse**. Verificare il nome del gruppo di risorse, quindi fare clic su **Elimina**. Monitorare la pagina **Notifiche** per verificare l'avanzamento dell'eliminazione.
