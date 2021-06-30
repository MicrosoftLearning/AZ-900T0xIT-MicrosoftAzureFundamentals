---
wts:
    title: '06 - Creare un database SQL (5 min)'
    module: 'Modulo 02 - Descrizione dei servizi principali di Azure (carichi di lavoro)'
---

# 06 - Creare un database SQL

In questa procedura dettagliata verrà creato un database SQL in Azure e quindi verrà eseguita una query sui relativi dati.

# Attività 1. Creare il database (5 min)

In questa attività verrà creato un database SQL basato sul database di esempio AdventureWorksLT. 

1. Accedere al portale di Azure all'indirizzo [**https://portal.azure.com**](https://portal.azure.com).

2. Nel pannello **Tutti i servizi** cercare e selezionare **Database SQL**, quindi fare clic su **+ Aggiungi, + Crea oppure + Nuovo**. 

3. Nella scheda **Informazioni di base** inserire queste informazioni  

    | Impostazione | Valore | 
    | --- | --- |
    | Sottoscrizione | **Scegliere le propria sottoscrizione** |
    | Gruppo di risorse | **myRGDb** (Crea nuovo) |
    | Nome database| **db1** | 
    | | |

3. Accanto all'elenco a discesa **Server** fare clic su **Crea nuovo** e immettere queste informazioni (sostituire **xxxx** nel nome del server con lettere e numeri in modo che il nome sia univoco a livello globale). Al termine, fare clic su **OK**.

    | Impostazione | Valore | 
    | --- | --- |
    | Nome server | **sqlserverxxxx** (deve essere univoco) | 
    | Accesso amministratore server | **sqluser** |
    | Password | **Pa$$w0rd1234** |
    | Località | **(Stati Uniti) Stati Uniti orientali** |
    | Consenti ai servizi di Azure di accedere al server| ***Selezionare la casella di controllo*** |
    | | |

   ![Screenshot del riquadro Server e del riquadro Nuovo server con i campi compilati come indicato nella tabella e i pulsanti Rivedi e crea e OK evidenziati.](../images/0501.png)

4. Passare alla scheda **Rete** e configurare le impostazioni seguenti (lasciare i valori predefiniti per le altre impostazioni) 

    | Impostazione | Valore | 
    | --- | --- |
    | Metodo di connettività | **Endpoint pubblico** |    
    | Consenti alle risorse e ai servizi di Azure di accedere a questo server | **Sì** |
    | Aggiungi indirizzo IP client corrente | **No** |
    | | |
    
   ![Screenshot della scheda Rete del pannello Crea database SQL con le impostazioni selezionate come indicato nella tabella e il pulsante Rivedi e crea evidenziato.](../images/0501b.png)

5. Passare alla scheda **Impostazioni aggiuntive**. Verrà usato il database di esempio AdventureWorksLT.

    | Impostazione | Valore | 
    | --- | --- |
    | Usa dati esistenti | **Esempio** |
    | Regole di confronto | ***usare l'impostazione predefinita*** |
    | Abilita Azure Defender per SQL | **Non adesso** |
    | | |

    ![Screenshot della scheda Impostazioni aggiuntive del pannello Crea database SQL con le impostazioni selezionate come indicato nella tabella e il pulsante Rivedi e crea evidenziato.](../images/0501c.png)

6. Fare clic su **Rivedi e crea** e quindi su **Crea** per distribuire il gruppo di risorse, il server e il database ed effettuarne il provisioning. La distribuzione può richiedere approssimativamente 2-5 minuti.

7. Passare alla scheda della risorsa per individuare il database SQL creato. Può essere necessario aggiornare.

# Attività 2. Testare il database.

In questa attività verrà configurato il server SQL e verrà eseguita una query SQL. 

1. Nel pannello **Tutti i servizi** cercare e selezionare **Database SQL**, quindi assicurarsi che il nuovo database sia stato creato. Può essere necessario scegliere **Aggiorna** per aggiornare la pagina.

    ![Screenshot del database SQL e del server appena distribuiti.](../images/0502.png)

2. Fare clic sulla voce **db1**, che rappresenta il database SQL creato, quindi fare clic su **Editor di query (anteprima)**.

3. Accedere con il nome utente **sqluser** e la password **Pa$$w0rd1234**.

4. Non sarà possibile eseguire l'accesso. Leggere attentamente il messaggio di errore e prendere nota dell'indirizzo IP che è necessario autorizzare attraverso il firewall. 

    ![Screenshot della pagina di accesso all'editor di query con il messaggio di errore relativo all'indirizzo IP.](../images/0503.png)

5. Nel pannello **db1** fare clic su **Panoramica**. 

    ![Screenshot della pagina del server SQL.](../images/0504.png)

6. Nel pannello **Panoramica** del server SQL fare clic su **Imposta firewall server**.

7. Fare clic su **Aggiungi IP client** nel menu della barra superiore per aggiungere l'indirizzo IP indicato nel messaggio di errore. Assicurarsi di scegliere **Salva** per salvare le modifiche. 

    ![Screenshot della pagina di impostazioni del firewall del server SQL con la nuova regola IP evidenziata.](../images/0506.png)

8. Tornare nel database SQL e nella pagina di accesso a **Editor di query (anteprima)**. Riprovare a eseguire l'accesso con il nome utente **sqluser** e la password **Pa$$w0rd1234**. Questa volta l'accesso dovrebbe riuscire. Tenere presente che la distribuzione della nuova regola del firewall può richiedere un paio di minuti. 

9. Una volta eseguito correttamente l'accesso, viene visualizzato il riquadro delle query. Immettere la query seguente nel riquadro dell'editor.

    ```SQL
    SELECT TOP 20 pc.Name as CategoryName, p.name as ProductName
    FROM SalesLT.ProductCategory pc
    JOIN SalesLT.Product p
    ON pc.productcategoryid = p.productcategoryid;
    ```

    ![Screenshot dell'editor di query con il riquadro delle query e i comandi eseguiti correttamente.](../images/0507.png)

10. Fare clic su **Esegui** e quindi esaminare i risultati della query nel riquadro **Risultati**. La query dovrebbe essere eseguita correttamente.

    ![Screenshot del riquadro Editor di query con il codice SQL eseguito correttamente e l'output visibile nel riquadro dei risultati.](../images/0508.png)

Congratulazioni! È stato creato un database SQL in Azure ed è stata eseguita correttamente una query sui relativi dati.

**Nota**: per evitare costi aggiuntivi, è possibile rimuovere questo gruppo di risorse. Cercare e selezionare il gruppo di risorse, quindi fare clic su **Elimina gruppo di risorse**. Verificare il nome del gruppo di risorse, quindi fare clic su **Elimina**. Monitorare la pagina **Notifiche** per verificare l'avanzamento dell'eliminazione.
