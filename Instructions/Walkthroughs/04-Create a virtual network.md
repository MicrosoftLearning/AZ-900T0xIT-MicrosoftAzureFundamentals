---
wts:
    title: '04 - Creare una rete virtuale (20 min)'
    module: 'Modulo 02 - Descrizione dei servizi principali di Azure (carichi di lavoro)'
---
# 04. Creare una rete virtuale (20 min)

In questa procedura dettagliata verrà creata una rete virtuale in cui verranno distribuite due macchine virtuali, che verranno configurate per consentire a una macchina virtuale di effettuare il ping all'altra all'interno della rete virtuale creata.

# Attività 1. Creare una rete virtuale 

In questa attività verrà creata una rete virtuale. 

Nota: prima di iniziare il lab, disabilitare il firewall pubblico e privato nella macchina virtuale aprendo il menu Start > Impostazioni > Rete e Internet > Windows Firewall.

1. Accedere al portale di Azure all'indirizzo <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a>

2. Nel pannello **Tutti i servizi** cercare e selezionare **Reti virtuali**, quindi fare clic su **+ Aggiungi, + Crea, + Nuovo**. 

3. Nella scheda **Informazioni di base** inserire le informazioni seguenti (lasciare i valori predefiniti per tutto il resto):

    | Impostazione | Valore | 
    | --- | --- |
    | Sottoscrizione | **Lasciare l'impostazione predefinita fornita** |
    | Gruppo di risorse | **Crea nuovo gruppo di risorse** |
    | Nome | **vnet1** |
    | Area | **(Stati Uniti) Stati Uniti orientali** |
    
   
4. Fare clic sul pulsante **Rivedi e crea**. Assicurarsi che la convalida venga superata. Fare quindi clic su Crea per distribuire la risorsa.


# Attività 2. Creare due macchine virtuali

In questa attività verranno create due macchine virtuali nella rete virtuale. 

1. Nel pannello **Tutti i servizi** cercare e selezionare **Macchine virtuali**, quindi fare clic su **+ Aggiungi, + Crea, + Nuovo** e dall'elenco a discesa selezionare **Macchina virtuale**. 

2. Nella scheda **Informazioni di base** inserire le informazioni seguenti (lasciare i valori predefiniti per tutto il resto):

   | Impostazione | Valore | 
   | --- | --- |
   | Sottoscrizione | **Usare l'impostazione predefinita fornita** |
   | Gruppo di risorse |  **Selezionare l'impostazione predefinita nell'elenco a discesa** |
   | Nome della macchina virtuale | **vm1**|
   | Area | **(Stati Uniti) Stati Uniti orientali** |
   | Immagine | **Windows Server 2019 Datacenter - Gen2** |
   | Nome utente| **azureuser** |
   | Password| **Pa$$w0rd1234** |
   | Porte in ingresso pubbliche| Selezionare **Consenti porte selezionate**  |
   | Selezionare le porte in ingresso| **RDP (3389)** |
   

3. Selezionare la scheda **Rete**. Accertarsi che la macchina virtuale venga inserita nella rete virtuale **vnet1**. Esaminare le impostazioni predefinite, ma non apportare altre modifiche. 

4. Fare clic su **Rivedi e crea**. Una volta superata la convalida, fare clic su **Crea**. I tempi di distribuzione variano, ma in genere sono necessari da tre a sei minuti.

5. Monitorare la distribuzione, ma continuare con il passaggio successivo. 

6. Creare una seconda macchina virtuale ripetendo i passaggi **da 2 a 4** precedenti. Verificare che la macchina virtuale abbia un nome diverso, sia inserita nella stessa rete virtuale e usi un nuovo indirizzo IP pubblico:

    | Impostazione | Valore |
    | --- | --- |
    | Gruppo di risorse | **selezionare il gruppo predefinito nell'elenco a discesa (come per l'attività 1-3 e l'attività 2-2)** |
    | Nome della macchina virtuale |  **vm2** |
    | Rete virtuale | **vnet1** |
    | IP pubblico | **vm2-ip** |

7. Attendere che entrambe le macchine virtuali vengano distribuite e che il loro stato indichi *in esecuzione*.

# Attività 3. Testare la connessione 

In questa attività verrà testata la capacità delle macchine virtuali di comunicare (effettuare il ping) tra di loro. Se la comunicazione non funziona, verrà installata una regola per consentire una connessione ICMP. In genere, le connessioni ICMP vengono bloccate automaticamente.

1. Nel pannello **Tutte le risorse** cercare **vm1**, aprire il relativo pannello **Panoramica** e verificare che per **Stato** sia visualizzato **In esecuzione**. Può essere necessario scegliere **Aggiorna** per aggiornare la pagina.

2. Nel pannello **Panoramica**, fare clic su **Connetti** e dall'elenco a discesa selezionare **RDP**.

    **Nota**: le istruzioni seguenti indicano come connettersi alla VM da un computer Windows. 

3. Nel pannello **Connetti con RDP** mantenere le opzioni predefinite per connettersi tramite l'indirizzo IP sulla porta 3389, quindi fare clic su **Scarica file RDP**.

4. Aprire il file RDP scaricato (visualizzato in basso a sinistra sulla VM), quindi fare clic su **Connetti** quando richiesto. 

5. Nella finestra **Sicurezza di Windows** digitare il nome utente **azureuser** e la password **Pa$$w0rd1234**, quindi fare clic su **OK**.

6. Durante la procedura di accesso, è possibile che venga visualizzato un avviso relativo al certificato. Fare clic su **Sì** per creare la connessione e connettersi alla VM distribuita. La connessione dovrebbe essere stabilita correttamente. Chiudere le finestre di Windows Server e del dashboard che si aprono. Si dovrebbe vedere lo sfondo blu di Windows. Ora ci si trova nella macchina virtuale.

Nota: nella macchina virtuale appena creata, disabilitare il firewall pubblico e privato aprendo il menu Start > Impostazioni > Rete e Internet > Windows Firewall.

7. Aprire PowerShell sulla macchina virtuale facendo clic sul pulsante **Avvia**, digitare **PowerShell** nella casella Cerca, quindi fare clic con il pulsante destro del mouse su **Windows PowerShell** e selezionare **Esegui come amministratore**

8. In Powershell, tentare di effettuare il ping a vm2 digitando il comando:

   ```PowerShell
   ping vm2
   ```

 9. La comunicazione dovrebbe riuscire. È stato effettuato il ping a VM2 da VM1.


**Congratulazioni!** Sono state configurate e distribuite due macchine virtuali in una rete virtuale e si è riusciti a metterle in comunicazione.

**Nota**: per evitare costi aggiuntivi, opzionalmente è possibile rimuovere questo gruppo di risorse. Cercare e selezionare il gruppo di risorse, quindi fare clic su **Elimina gruppo di risorse**. Verificare il nome del gruppo di risorse, quindi fare clic su **Elimina**. Monitorare la pagina **Notifiche** per verificare l'avanzamento dell'eliminazione.
