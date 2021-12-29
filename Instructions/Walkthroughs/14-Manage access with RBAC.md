---
wts:
    title: '14 - Gestire l'accesso con il controllo degli accessi in base al ruolo (5 min)'
    module: 'Modulo 05: Descrizione delle funzionalità di identità, governance, privacy e conformità'
---
# 14 - Gestire l'accesso con il controllo degli accessi in base al ruolo (5 min)

In questa procedura dettagliata verranno assegnati ruoli di autorizzazione alle risorse e verranno visualizzati i log.

# Attività 1. Visualizzare e assegnare i ruoli

In questa attività verrà assegnato il ruolo Collaboratore Macchina virtuale. 

1. Accedere al [portale di Azure](https://portal.azure.com).

2. Nel pannello **Tutti i servizi** cercare e selezionare **Gruppi di risorse**, quindi fare clic su **+ Aggiungi + Nuovo + Crea**.

3. Creare un nuovo gruppo di risorse. Al termine, fare clic su **Crea**. 

    | Impostazione | Valore |
    | -- | -- |
    | Sottoscrizione | **Usare l'impostazione predefinita fornita** |
    | Gruppo di risorse | **myRGRBAC** |
    | Area | **(Stati Uniti) Stati Uniti orientali** |
   

4. Fare clic su **Rivedi e crea** e quindi su **Crea**.

5. Scegliere **Aggiorna** per aggiornare la pagina del gruppo di risorse, quindi fare clic sulla voce che rappresenta il nuovo gruppo di risorse creato.

6. Fare clic sul pannello **Controllo di accesso (IAM)** e quindi passare alla scheda **Ruoli**. Scorrere il numero elevato di definizioni dei ruoli disponibili. Usare le icone di informazioni per avere un'idea delle autorizzazioni di ogni ruolo. Sono anche disponibili informazioni sul numero di utenti e gruppi assegnati a ogni ruolo.

![immagine](https://user-images.githubusercontent.com/89808319/144266949-f19d91ab-31d6-4c8b-af36-c00035925cf0.png)

7. Passare alla scheda **Assegnazioni di ruolo** del pannello **myRGRBAC - Controllo di accesso (IAM)**, fare clic su **+ Aggiungi** e quindi fare clic su **Aggiungi assegnazione di ruolo**. Cercare il ruolo Virtual Machine Contributor e selezionarlo. Passare alla scheda "Membri" e assegnare l'accesso a: Utente, gruppo o entità servizio. Quindi fare clic su + Selezionare membri e digitare il proprio nome nella funzione di ricerca popup e premere "seleziona". Quindi premere "Verifica e assegna"

    
    ![immagine](https://user-images.githubusercontent.com/89808319/144266255-3a0f8574-9358-4c21-8f95-3503747e77c8.png)

 

    **Nota:** il ruolo Collaboratore Macchina virtuale consente di gestire le macchine virtuali, ma non di accedere al relativo sistema operativo né di gestire la rete virtuale e l'account di archiviazione a cui sono connesse.

  

8. Scegliere **Aggiorna** per aggiornare la pagina Assegnazioni di ruolo e verificare che il proprio account utente sia ora indicato come Collaboratore Macchina virtuale. 

    **Nota**: questa assegnazione non concede in realtà privilegi aggiuntivi, perché il proprio account ha già il ruolo Proprietario, che include tutti i privilegi associati al ruolo Collaboratore.

# Attività 2. Monitorare le assegnazioni di ruolo e rimuovere un ruolo

In questa attività verrà visualizzato il log attività per verificare l'assegnazione del ruolo, quindi verrà rimosso il ruolo. 

1. Nel pannello del gruppo di risorse myRGRBAC fare clic su **Log attività**.

2. Fare clic su **Aggiungi filtro**, selezionare **Operazione** e quindi **Crea assegnazione ruolo**.

    ![Screenshot della pagina Log attività con il filtro configurato.](../images/1503.png)

3. Verificare che il log attività visualizzi l'assegnazione di ruolo. 

    **Nota**: si riesce a capire come rimuovere l'assegnazione di ruolo?

Congratulazioni! È stato creato un gruppo di risorse, gli è stato assegnato un ruolo di accesso e sono stati visualizzati i log attività. 

**Nota**: per evitare costi aggiuntivi, è possibile rimuovere questo gruppo di risorse. Cercare e selezionare il gruppo di risorse, quindi fare clic su **Elimina gruppo di risorse**. Verificare il nome del gruppo di risorse e quindi fare clic su **Elimina**. Monitorare la pagina **Notifiche** per verificare l'avanzamento dell'eliminazione.

