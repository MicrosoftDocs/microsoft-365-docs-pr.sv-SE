---
title: Ansluta till Exchange Online-klient organisationer med Windows PowerShell för DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Sammanfattning: Använd Windows PowerShell för att ansluta till Exchange Online genom att använda DelegatedOrg-värdet.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694673"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Ansluta till Exchange Online-klient organisationer med Windows PowerShell-partner för delegerade åtkomst behörigheter (DAP)

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

> [!IMPORTANT]
> Procedurerna i det här avsnittet gäller endast för DAP-partners (delegerade åtkomst behörigheter). Om du inte är en DAP-partner, Använd inte procedurerna i det här avsnittet. 
  
DAP partners är syndikerings-och Cloud solution providers (CSP)-partners. De är ofta nätverks-eller Telekom-leverantörer i andra företag. De kan skicka abonnemang till sina tjänster till sina kunder. De äger en partner innehavaren som automatiskt ges tillstånd att administrera (AOBO) till sina Microsoft 365-kund innehavare så att de kan administrera och rapportera om sina kund innehavare.

DAP partners kan använda Exchange Online PowerShell för att hantera inställningar för kund Exchange Online och få Microsoft 365-rapporter från kommando raden. Du använder Windows PowerShell på din lokala dator för att skapa en fjärrsession för PowerShell till Exchange Online. Det är en enkel tre stegs process där du anger dina inloggnings uppgifter, ger nödvändiga anslutnings inställningar och importerar sedan Exchange Online-cmdlets till din lokala Windows PowerShell-session så att du kan använda dem.

> [!NOTE]
> DAP partners kan inte använda proceduren i [ansluta till Exchange Online PowerShell med multifaktorautentisering](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) för att ansluta till deras kund klient organisationer i Exchange Online PowerShell. MFA och Exchange Online Remote PowerShell-modulen fungerar inte med delegerad auktorisering.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid: 5 minuter

- Du kan använda följande versioner av Windows:
    
  - Windows 10

  - Windows 8,1

  - Windows Server 2016

  - Windows Server 2012 eller Windows Server 2012 R2

  - Windows 7 Service Pack 1 (SP1)<sup>*</sup>

  - Windows Server 2008 R2 SP1<sup>*</sup>

    <sup>*</sup> Om du har en äldre version av Windows måste du installera Microsoft.NET Framework 4,5 eller senare och sedan en uppdaterad version av Windows Management Framework: 3,0, 4,0 eller 5,1 (endast en). Mer information finns i [Installera .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [windows Management Framework 3,0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/p/?LinkId=391344)och [Windows Management Framework 5,1](https://aka.ms/wmf5download).

- Windows PowerShell måste konfigureras för att köra skript och som standard är det inte. Du får följande fel meddelande när du försöker ansluta:

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  Om du vill att alla PowerShell-skript som du laddar ned från Internet är signerade av en betrodd utgivare kör du följande kommando i ett förhöjdt fönster i Windows PowerShell (ett fönster i Windows PowerShell som du öppnar genom att välja **Kör som administratör**):

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  Du behöver bara konfigurera den här inställningen en gång på datorn, inte varje gång du ansluter.

- Information om kortkommandon som kan gälla procedurerna i det här avsnittet finns i kortkommandon [i administrations centret för Exchange](https://go.microsoft.com/fwlink/p/?LinkId=534017).

## <a name="connect-to-exchange-online-for-customer-organizations"></a>Ansluta till Exchange Online för kund organisationer

1. Öppna Windows PowerShell på din lokala dator och kör följande kommando.
    
    ```
    $UserCredential = Get-Credential
    ```

    I dialog rutan **begäran om autentiseringsuppgifter för Windows PowerShell** anger du DAP administratörs namn och lösen ord och klickar sedan på **OK**.
    
2. Ersätt _\<customer tenant domain name\>_ med namnet på den klient organisation som du vill ansluta till och kör följande kommando:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    Huvud steget i det här kommandot anger vilken kund som får åtkomst till rapporterings informationen. Det gör du i parametern  _ConnectionURI_ där du anger FQDN för det ursprungliga domän namnet som värde för `?DelegatedOrg=` . Det här värdet anger korrekt PowerShell-slutpunkt för Exchange Online för att ansluta till. Fjärrpowershell måste ansluta till Microsoft 365 repor ting i kontexten för en viss kund varje gång en rapport körs. När du har anslutit till Exchange Online PowerShell körs alla efterföljande kommandon i kontexten för kunden, vilket ger dig till gång till alla tillgängliga rapporter för kunden.
    
3. Kör följande kommando.
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> Det finns en gräns på tre samtidiga sessioner som kan köras under ett konto. Koppla bort fjärrsessionen för PowerShell när du är klar. Om du stänger Windows PowerShell-fönstret utan att koppla bort sessionen kan du använda upp alla fjärrsessioner som är tillgängliga för dig och du måste vänta tills sessionerna upphör att gälla. Om du vill koppla bort fjärrsessionen från PowerShell kör du följande kommando:

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Efter steg 3 importeras Exchange Online-cmdlets till din lokala Windows PowerShell-session som spåras av en förlopps indikator. Om du inte får några problem har du lyckats ansluta. En snabb test är att köra en Exchange Online-cmdlet (till exempel **Get-postlåda**) och se resultatet.
  
Om du får fel meddelanden bör du kontrol lera följande:
  
- Ett vanligt problem är felaktigt lösen ord. Kör de tre stegen igen och betala nära till det användar namn och lösen ord som du angav i steg 1.
    
- Det konto som du använder för att ansluta till Exchange Online måste vara aktiverat för fjärr-PowerShell. Mer information finns i [Aktivera eller inaktivera åtkomst till Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).
    
- TCP-port 80-trafik måste vara öppen mellan din lokala dator och Exchange Online. Det är troligt men det är något att överväga om din organisation har en begränsad Internet åtkomst policy.
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a>Anropa cmdlet direkt med kommandot Invoke-Command

Det kan vara en lång tids krävande att importera en fjärrsession i PowerShell (steg 3) eftersom den kommer med i _alla_ Exchange Online-cmdletar. Detta kan vara ett problem i grupp bearbetning (till exempel när du kör rapporter eller skapar Mass ändringar för olika innehavare). Som ett alternativ till att använda **import-PSSession**kan du ringa cmdletar som du vill använda direkt med **kommandot Invoke-**. Om du till exempel vill anropa cmdleten **Get-Milbox** ersätter du `Import-PSSession $Session` kommandot i steg 3:
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a>Fler cmdlets för rapportering

De cmdlets som du använde i det här avsnittet är Windows PowerShell-cmdletar. Mer information om dessa cmdletar finns i följande avsnitt:
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

