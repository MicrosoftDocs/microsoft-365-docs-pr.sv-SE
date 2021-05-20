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
description: Lär dig hur du dirigerar trafik till en befintlig offentlig webbplats utanför Microsoft, om du har ställt in Microsoft att hantera DNS-poster för din anpassade domän.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572147"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell

 **Om du hanterar domänens Microsoft-poster hos din DNS-värd** behöver du inte oroa dig för stegen i det här avsnittet. Din webbplats finns kvar på samma plats och användarna kan fortfarande komma åt den. 
  
 **Om Microsoft hanterar dina DNS-poster** gör du följande för att dirigera trafik till en befintlig offentlig webbplats som finns utanför Microsoft: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Uppdatera DNS-poster i Microsoft 365 administrationscenter
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

1. På sidan **Domäner** väljer du domänen och väljer sedan **DNS-poster**.

1. Välj **+ Lägg till** post och ange följande: 
    
   - För **typ** anger: **A (Adress)**
    
   - I **Värdnamn eller alias** skriver du in **@**
    
   - I **IP-adress** skriver du in den statiska IP-adress där webbplatsen finns för närvarande (till exempel 172.16.140.1). 
    
   Det måste vara en  *statisk*  IP-adress för webbplatsen, inte en  *dynamisk*  IP-adress.Kontrollera med webbplatsen som är värd för din webbplats för att se till att du kan få en statisk IP-adress till din offentliga webbplats. 
    
1. Välj **Spara**. 
    
Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.
  
1. Välj **+ Lägg till** post och ange följande: 
    
   - För **typ** anger: **CNAME (Alias)**
    
   - I **Värdnamn eller alias** skriver du in **www**
    
   - I **Pekar på adress** skriver du in det fullständiga domännamnet (FQDN) för webbplatsen (till exempel contoso.com). 
    
2. Välj **Spara**. 
    
Gör sedan följande:
  
[Uppdatera domänens NS-poster så att](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) de pekar på Microsoft. 
  
När NS-posterna har uppdaterats för att peka på Microsoft är din domän konfigurerad. E-post dirigeras till Microsoft och trafiken till din webbplatsadress fortsätter att gå till din nuvarande webbplatsvärd.
