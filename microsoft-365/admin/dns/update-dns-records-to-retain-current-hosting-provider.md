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
description: Lär dig hur du dirigerar trafik till en befintlig offentlig webbplats som finns utanför Office 365 om du har angett att Office 365 ska hantera DNS-poster för din anpassade domän.
ms.openlocfilehash: b92e778fb2fe0353a0d1d6bf83a4c617ab4541e2
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811561"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell

 **Om du hanterar din domäns Office 365-poster hos din DNS-värd** behöver du inte bry dig om anvisningarna i det här avsnittet. Din webbplats finns kvar på samma plats och användarna kan fortfarande komma åt den. 
  
 **Om Office 365 hanterar dina DNS-poster** och du vill dirigera trafik till en befintlig offentlig webbplats som inte ligger i Office 365, gör du följande när du har lagt till din domän i Office 365: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Uppdatera DNS-poster i microsoft 365-administrationscentret
1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>

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
  
[Uppdatera domänens NS-poster](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) så att de pekar på Office 365. 
  
När du har uppdaterat NS-posterna så att de pekar på Office 365 är domänen färdigkonfigurerad. All e-post kommer hädanefter att dirigeras till Office 365, och trafiken till webbadressen kommer att fortsätta att gå till det nuvarande webbhotellet.
 
