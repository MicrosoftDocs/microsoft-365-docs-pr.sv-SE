---
title: Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Lär dig hur du dirigerar trafik till en befintlig offentlig webbplats som inte finns hos Microsoft, om du har ställt in Microsoft på att hantera DNS-poster för din egen domän.
ms.openlocfilehash: ceef82345e562e2aa4c291f416c454fb831ee45b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915980"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell

 **Om du hanterar domänens Microsoft-poster hos din DNS-värd** behöver du inte bry dig om stegen i det här avsnittet. Din webbplats finns kvar på samma plats och användarna kan fortfarande komma åt den. 
  
 **Om Microsoft hanterar dina DNS-poster gör** du följande för att dirigera trafik till en befintlig offentlig webbplats som finns utanför Microsoft, gör du följande när du har lagt till din domän i Microsoft: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Uppdatera DNS-poster i administrationscentret för Microsoft 365
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

2. På sidan **Domains** väljer du domänen och sedan **DNS Records.**

3. Välj **Anpassade poster** under **DNS-inställningar.**

4. Välj **+ Ny anpassad post** och ange följande: 
    
   - Ange följande för **DNS-typ**: **A (adress)**
    
   - I **Värdnamn eller alias** skriver du in **@**
    
   - I **IP-adress** skriver du in den statiska IP-adress där webbplatsen finns för närvarande (till exempel 172.16.140.1). 
    
   Det måste vara en  *statisk*  IP-adress för webbplatsen, inte en  *dynamisk*  IP-adress.Kontrollera med webbplatsen som är värd för din webbplats för att se till att du kan få en statisk IP-adress till din offentliga webbplats. 
    
5. Välj **Spara**. 
    
Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.
  
1. Välj **+ Ny anpassad post** och ange följande: 
    
   - Ange följande för **DNS-typ**: **CNAME (alias)**
    
   - I **Värdnamn eller alias** skriver du in **www**
    
   - I **Pekar på adress** skriver du in det fullständiga domännamnet (FQDN) för webbplatsen (till exempel contoso.com). 
    
2. Välj **Spara**. 
    
Gör sedan följande:
  
[Uppdatera domänens NS-poster så](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) att de pekar på Microsoft. 
  
När NS-posterna har uppdaterats så att de pekar på Microsoft är din domän konfigurerad. E-post kommer att dirigeras till Microsoft och trafiken till din webbplatsadress kommer fortsätta att gå till din nuvarande webbplatsvärd.
