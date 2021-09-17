---
wts:
    title: '21 - Calcolare i contratti di servizio compositi (5 min)'
    module: 'Modulo 06: Descrizione di Gestione costi di Azure e Contratti di servizio'
---
# 21. Calcolare i Contratti di servizio compositi (5 min)'

In questa procedura dettagliata verrà determinata la disponibilità di contratti di servizio per i servizi di Azure e quindi verrà calcolata la disponibilità prevista basata sul contratto di servizio composito per un'applicazione.

L'applicazione di esempio è costituita da questi servizi di Azure. Non verranno forniti approfondimenti e considerazioni sulla configurazione dell'architettura, perché l'intenzione è offrire un esempio generale.

+ **Servizio app**: per ospitare l'applicazione.
+ **Azure AD B2C**: per autenticare gli accessi utente e gestire i profili.
+ **Gateway applicazione**: per gestire l'accesso all'applicazione e la scalabilità. 
+ **Database SQL di Azure**: per archiviare i dati dell'applicazione. 

# Attività 1. Determinare i valori in percentuale del tempo di attività del Contratto di servizio per l'applicazione

1. In un browser passare alla pagina [Riepilogo dei contratti di servizio per i servizi di Azure](https://azure.microsoft.com/it-it/support/legal/sla/summary/).

2. Individuare il valore del tempo di attività del contratto di servizio per **Servizio app**, **99,95%**. Fare clic su **L'utente deve visualizzare i dettagli completi** e quindi espandere **Dettagli del Contratto di Servizio**. Leggere le sezioni **Percentuale del Tempo di Attività Mensile** e **Credito di Servizio**.

3. Tornare nella pagina Web dei contratti di servizio e individuare il servizio **Azure Active Directory B2C**. Il valore del tempo di attività del contratto di servizio è **99,9%**. 

4. Individuare il valore del tempo di attività del contratto di servizio per **Gateway applicazione**, **99,95%**. 

5. Il database SQL di Azure usa livelli Premium ma non è configurato per distribuzioni con ridondanza della zona. Individuare il valore del tempo di attività del contratto di servizio per **Database SQL di Azure**, **99,99%**. 

    **Nota**: esistono valori del tempo di attività diversi per le varie configurazioni e distribuzioni del database SQL di Azure. È importante sapere con certezza i valori richiesti del tempo di attività quando si pianificano la distribuzione e la configurazione e si determinano i relativi costi. Piccole modifiche nel tempo di attività possono avere un impatto sui costi dei servizi, oltre ad aumentare eventualmente la complessità della configurazione. Altri servizi che potrebbero essere interessanti nella pagina Web di riepilogo dei contratti di servizio di Azure sono **Macchine virtuali**, **Account di archiviazione** e **Cosmos DB**.

# Attività 2. Calcolare il tempo di attività in percentuale del contratto di servizio composito per un'applicazione

1. Se i servizi che compongono l'applicazione non sono disponibili, l'applicazione non sarà disponibile per l'accesso e l'uso da parte degli utenti. Di conseguenza il tempo di attività totale per l'applicazione è costituito da quanto segue:

    **% del tempo di attività del servizio app** X **% del tempo di attività di Azure AD B2C** X **% del tempo di attività del gateway applicazione di Azure** X **% del tempo di attività del database SQL di Azure** = **% totale del tempo di attività**

    che in termini di percentuale equivale a:

    **99,95%** X **99,9%** X **99,95%** X **99,99%** = **99,79%**

    Questa è la disponibilità prevista basata sul contratto di servizio dell'applicazione con i servizi e l'architettura correnti.

Congratulazioni! È stato determinato il tempo di attività basato sul contratto di servizio per ogni servizio dell'applicazione di esempio e quindi è stata calcolata la disponibilità prevista basata sul contratto di servizio composito per l'applicazione.
