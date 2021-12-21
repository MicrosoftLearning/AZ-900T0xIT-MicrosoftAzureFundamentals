---
wts:
    title: '02 - Creare un’app Web (10 min)'
    module: 'Modulo 02 - Descrizione dei servizi principali di Azure (carichi di lavoro)'
---
# 02. Creare un'app Web (10 min)

In questa procedura dettagliata verrà creata una nuova app Web che esegue un contenitore Docker. Il contenitore Docker include un messaggio di benvenuto. 

Il Servizio app di Azure è in realtà una raccolta di quattro servizi, tutti progettati per consentire l'hosting e l'esecuzione di applicazioni Web. I quattro servizi (App Web, App per dispositivi mobili, App per le API e App per la logica) sembrano diversi, ma in definitiva funzionano tutti in modo molto simile. In questo lab verrà usato il servizio App Web, che è quello usato più comunemente tra i quattro.

# Attività 1. Creare un'app Web 

In questa attività verrà creata un'app Web del servizio app di Azure. 

1. Accedere al [portale di Azure](http://portal.azure.com/). 

2. Nel pannello **Tutti i servizi** cercare e selezionare **Servizi app**, quindi fare clic su **+ Aggiungi, + Crea, + Nuovo**.

3. Nella scheda **Informazioni di base** del pannello **App Web** specificare le impostazioni seguenti (sostituire **xxxx** nel nome dell'app Web con lettere e numeri in modo che il nome sia univoco a livello globale). Lasciare i valori predefiniti per tutto il resto, incluso il piano di servizio app. 

    | Impostazione | Valore |
    | -- | -- |
    | Sottoscrizione | **Usare l'impostazione predefinita fornita** |
    | Gruppo di risorse | **Creare nuovo gruppo di risorse**|
    | Nome | **myDockerWebAppxxxx** |
    | Pubblica | **Contenitore Docker** |
    | Sistema operativo | **Linux** |
    | Area | **Stati Uniti orientali** |
    
    **Nota:** non dimenticare di modificare **xxxx** in modo che il nome dell'app Web sia univoco a livello globale.

4. Fare clic su **Avanti > Docker** e configurare le informazioni sul contenitore.  

    | Impostazione | Valore |
    | -- | -- |
    | Opzioni | **Contenitore singolo** |
    | Origine immagine | **Docker Hub** |
    | Tipo di accesso | **Pubblico** |
    | Immagine e tag | **mcr.microsoft.com/azuredocs/aci-helloworld** |
    
 **Nota:** il comando di avvio è facoltativo e non è necessario in questo esercizio.

5. Fare clic su **Rivedi e crea** e quindi su **Crea**. 

# Attività 2. Testare l'app Web

In questa attività verrà testata l'app Web.

1. Attendere che l'app Web venga distribuita.

2. In **Notifiche** fare clic su **Vai alla risorsa**. 

3. Nel pannello **Panoramica** individuare l'**URL**. Copiare l'URL negli Appunti.

    ![Screenshot del pannello delle proprietà dell'app Web. L'URL è evidenziato.](../images/0801.png)

4. In una nuova finestra del browser, incollare l'URL e premere Invio. Viene visualizzato il messaggio Benvenuto in Istanze di Azure Container.

    ![Screenshot della pagina Benvenuto in Istanze di Azure Container.](../images/0802.png)

5. Tornare nel pannello **Panoramica** dell'app Web e scorrere verso il basso. Notare la presenza di diversi grafici che riportano i dati in ingresso/uscita e le richieste. Se si ripete per alcune volte il passaggio 4, sarà possibile visualizzare in questi grafici i dati di telemetria corrispondenti, tra cui il numero di richieste e il tempo medio di risposta. 

**Nota**: per evitare costi aggiuntivi, è possibile rimuovere questo gruppo di risorse. Cercare e selezionare il gruppo di risorse, quindi fare clic su **Elimina gruppo di risorse**. Verificare il nome del gruppo di risorse, quindi fare clic su **Elimina**. Monitorare la pagina **Notifiche** per verificare l'avanzamento dell'eliminazione.

Congratulazioni: è stata creata correttamente un'app Web del Servizio app di Azure.
