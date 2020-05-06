---
title: Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Lär dig hur du dirigerar trafik till en befintlig offentlig webbplats som finns utanför Microsoft om du har angett att Microsoft ska hantera DNS-poster för din anpassade domän.
ms.openlocfilehash: 58b58479a2c880cc0193058abc328cc5feea4af1
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048837"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell

 **Om du hanterar domänens Microsoft-poster hos din DNS-värd**behöver du inte oroa dig för stegen i det här avsnittet. Din webbplats finns kvar på samma plats och användarna kan fortfarande komma åt den. 
  
 **Om Microsoft hanterar dina DNS-poster**gör du följande när du har lagt till din domän i Microsoft: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Uppdatera DNS-poster i microsoft 365-administrationscentret
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

2. På sidan **Domäner**, i listan över domäner, väljer du den domän du använder för webbplatsen och väljer sedan **DNS-inställningar** i hanteringsfönstret. 
    
3. Välj **+ Ny anpassad post** och ange följande: 
    
  - Ange följande för **DNS-typ**: **A (adress)**
    
  - I **Värdnamn eller alias** skriver du in **@**
    
  - I **IP-adress** skriver du in den statiska IP-adress där webbplatsen finns för närvarande (till exempel 172.16.140.1). 
    
    Det måste vara en  *statisk*  IP-adress för webbplatsen, inte en  *dynamisk*  IP-adress.Kontrollera med webbplatsen som är värd för din webbplats för att se till att du kan få en statisk IP-adress till din offentliga webbplats. 
    
3. Välj **Spara**. 
    
Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.
  
1. Välj **+ Ny anpassad post** och ange följande: 
    
  - Ange följande för **DNS-typ**: **CNAME (alias)**
    
  - I **Värdnamn eller alias** skriver du in **www**
    
  - I **Pekar på adress** skriver du in det fullständiga domännamnet (FQDN) för webbplatsen (till exempel contoso.com). 
    
2. Välj **Spara**. 
    
Gör sedan följande:
  
[Uppdatera domänens NS-poster](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) så att de pekar på Microsoft. 
  
När NS-posterna har uppdaterats så att de pekar på Microsoft är domänen konfigurerad. E-post dirigeras till Microsoft och trafiken till din webbadress fortsätter att gå till din nuvarande webbplatsvärd.
 
