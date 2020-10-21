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
description: Lär dig hur du dirigerar trafik till en befintlig offentlig webbplats som ligger utanför Microsoft, om du har konfigurerat Microsoft för att hantera DNS-poster för din egen domän.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645569"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell

 **Om du hanterar din domäns Microsoft-poster hos din DNS-värd**behöver du inte oroa dig för stegen i det här avsnittet. Din webbplats finns kvar på samma plats och användarna kan fortfarande komma åt den. 
  
 **Om Microsoft hanterar dina DNS-poster**och dirigerar trafik till en befintlig offentlig webbplats som finns utanför Microsoft, efter att du har lagt till din domän i Microsoft, gör du följande: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Uppdatera DNS-poster i administrations centret för Microsoft 365
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

2. På sidan **domäner** väljer du domänen och sedan **DNS Records**.

3. Under **DNS-inställningar**väljer du **anpassade poster**.

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
  
[Uppdatera domänens NS-poster](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) så att de pekar på Microsoft. 
  
När NS-posterna har uppdaterats så att de pekar på Microsoft är din domän konfigurerad. E-postmeddelandet dirigeras till Microsoft och trafik till din webb adress fortsätter att gå till din aktuella webbplats värd.
 
