---
title: Konfigurera kryptering i Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Med Office 365 är vissa krypteringsfunktioner aktiverat som standard. Andra funktioner kan konfigureras för att uppfylla vissa efterlevnadskrav eller juridiska krav.
ms.openlocfilehash: f126e429e2c4601531ea419267c3a54a95bd76b4
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162749"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Konfigurera kryptering i Office 365 Enterprise

Kryptering kan skydda innehållet från att läsas av obehöriga användare. Eftersom [kryptering i Office 365](encryption.md) kan göras med olika tekniker och metoder finns det inte någon enda plats där du aktiverar eller ställer in kryptering. Den här artikeln innehåller information om olika sätt att konfigurera eller konfigurera kryptering som en del av din strategi för informationsskydd.
  
> [!TIP]
> Mer teknisk information om kryptering finns i Teknisk referensinformation [om kryptering i Office 365](technical-reference-details-about-encryption.md).
  
Med Office 365 är flera krypteringsfunktioner tillgängliga som standard. Ytterligare krypteringsfunktioner kan konfigureras för att uppfylla vissa efterlevnadskrav eller juridiska krav. I följande tabell beskrivs flera krypteringsmetoder för olika scenarier.
  
|**Scenario**|**Krypteringsmetoder**|
|:-----|:-----|
|Filer sparas på Windows datorer  <br/> |Kryptering på datornivå kan göras med hjälp av BitLocker på Windows enheter. Som företagsadministratör eller IT Pro kan du konfigurera detta med hjälp av Microsoft Deployment Toolkit (MDT). Se [Konfigurera MDT för BitLocker](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker).  <br/> |
|Filer sparas på mobila enheter  <br/> |Vissa typer av mobila enheter krypterar filer som sparas på dessa enheter som standard. Med [inbyggda funktioner i Mobile Device Management för Office 365](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)kan du ange principer som bestämmer om mobila enheter ska få åtkomst till data i Office 365. Du kan till exempel ange en princip som gör att endast enheter som krypterar innehåll kan komma åt Office 365 data. Se [Skapa och distribuera säkerhetsprinciper för enheter.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> Om du vill ha mer kontroll över hur mobila enheter interagerar Office 365 kan du lägga till [Microsoft Intune](/mem/intune/fundamentals/setup-steps).  <br/> |
|Du behöver kontroll över krypteringsnycklarna som används för att kryptera dina data i Microsofts datacenter  <br/> | Som Office 365 administratör kan du kontrollera organisationens krypteringsnycklar och sedan konfigurera Office 365 så att de använder dem för att kryptera dina data i vila i Microsofts datacenter.  <br/> [Tjänstkryptering med Kundnyckel i Office 365](customer-key-overview.md) <br/> |
|Personer kommunicerar via e-post (Exchange Online)  <br/> | Som administratör Exchange Online du flera alternativ för att konfigurera e-postkryptering. De omfattar:  <br/>  Använda [Office 365 meddelandekryptering (OME)](set-up-new-message-encryption-capabilities.md) med Azure Rights Management (Azure RMS) för att göra det möjligt för personer att skicka krypterade meddelanden inom eller utanför organisationen  <br/>  Använda [S/MIME för meddelandesignering och kryptering för](../security/office-365-security/s-mime-for-message-signing-and-encryption.md) att kryptera och signera e-postmeddelanden digitalt  <br/>  Använda TLS för [att konfigurera kopplingar för säkert e-postflöde med en annan organisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) <br/>  Läs [e-postkryptering i Office 365](./email-encryption.md).  <br/> |
|Filer nås från gruppwebbplatser eller dokumentbibliotek (OneDrive för företag eller SharePoint Online)  <br/> |När personer arbetar med filer som sparats i OneDrive för företag eller SharePoint Online används TLS-anslutningar. Det här är inbyggt i Office 365 automatiskt. Läs [Datakryptering i OneDrive för företag och SharePoint Online.](./data-encryption-in-odb-and-spo.md)  <br/> |
|Filer delas i onlinemöten och snabbmeddelandekonversationer (Skype för företag Online)  <br/> |När personer arbetar med filer med Skype för företag Online används TLS för anslutningen. Det här är inbyggt i Office 365 automatiskt. Se [Säkerhet och arkivering (Skype för företag Online).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)  <br/> |
|Filer delas i onlinemöten och snabbmeddelandekonversationer (Microsoft Teams)  <br/> |När personer arbetar med filer med Microsoft Teams, används TLS för anslutningen. Det här är inbyggt i Office 365 automatiskt. Microsoft Teams stöder för närvarande inte direkt rendering av krypterad e-post. Om du vill förhindra att krypterade e-postmeddelanden landar Microsoft Teams som krypterade kan du läsa Vanliga frågor och svar [om meddelandekryptering.](./ome-faq.yml?view=o365-worldwide&preserve-view=true#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)  <br/> 

## <a name="additional-information"></a>Ytterligare information

Mer information om filskyddslösningar som innehåller krypteringsalternativ finns i [Filskyddslösningar i Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
