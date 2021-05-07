---
title: E-postkryptering i Exchange Online med AD RMS
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du Exchange Online IRM för att använda en lokal AD RMS (Active Directory Rights Management Service) för att uppfylla organisationens krav.
ms.openlocfilehash: d98cf5c762cd4dac0cbad6d25a3cc766d5c5310a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162746"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>E-postkryptering i Exchange Online med AD RMS

För att förhindra det kan Exchange Online informationsläckor med IRM-funktioner (Information Rights Management) som skyddar e-postmeddelanden och bifogade filer både online och offline. Du kan konfigurera Exchange Online IRM för att använda en lokal AD RMS (Active Directory Rights Management Service) om det behövs för att uppfylla organisationens krav. Det är inte vanligt. Om du inte behöver använda AD RMS ska du [använda](ome.md) Meddelandekryptering i Office 365 stället. 

IRM-skydd kan tillämpas av användare i Microsoft Outlook eller Outlook på webben och det kan tillämpas av administratörer med hjälp av transportskyddsregler Outlook skyddsregler. Med IRM kan du och dina användare styra vem som kan komma åt, vidarebefordra, skriva ut eller kopiera känsliga data i ett e-postmeddelande.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Ändringar av hur IRM fungerar med Meddelandekryptering i Office 365 (OME) och Azure Active Directory

I september 2017, när du konfigurerade de nya Meddelandekryptering i Office 365-funktionerna för organisationen, konfigurerade du också IRM för användning med Azure Rights Management (Azure RMS). Du kan inte längre konfigurera IRM med Azure RMS separat. I stället fungerar OME- och rättighetshantering smidigt tillsammans. Mer information om de nya funktionerna finns i Vanliga frågor [och Meddelandekryptering i Office 365](./ome-faq.yml). Om du är redo att börja använda de nya OME-funktionerna i din organisation kan du gå till Konfigurera nya Meddelandekryptering i Office 365-funktioner som bygger på [Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Hur IRM fungerar med Exchange Online och Active Directory Rights Management Services

Exchange Online IRM använder lokal Active Directory Rights Management Services (AD RMS), en teknik för att skydda information i Windows Server 2008 och senare. IRM-skydd tillämpas på e-post genom att använda en principmall för AD RMS-rättigheter i ett e-postmeddelande. Rättigheter bifogas själva meddelandet så att skydd sker online och offline och inom och utanför organisationens brandvägg.
  
Användare kan använda en mall för ett e-postmeddelande för att styra vilka behörigheter som mottagare har för ett meddelande. Åtgärder, till exempel vidarebefordran, extrahera information från ett meddelande, spara ett meddelande eller skriva ut ett meddelande kan styras genom att använda en AD RMS-rättighetsprincip på meddelandet.
  
Du kan konfigurera IRM för att använda en AD RMS-server Windows Server 2008 eller senare. Du kan använda den här AD RMS-servern för att hantera policymallarna för AD RMS-rättigheter för din molnbaserade organisation. Outlook också förlitar sig på AD RMS-servern så att användarna kan tillämpa IRM-skydd på meddelanden som de skickar. Mer information finns i [Konfigurera IRM för att använda en lokal AD RMS-server.](configure-irm-to-use-an-on-premises-ad-rms-server.md) 
  
När det är aktiverat kan IRM-skydd tillämpas på meddelanden på följande sätt:
  
- **Användare kan använda en mall manuellt Outlook och Outlook på webben.** Användarna kan tillämpa en principmall för AD RMS-rättigheter i ett e-postmeddelande genom att välja mallen i **listan Ange** behörigheter. När användare skickar ett IRM-skyddat meddelande får alla bifogade filer som använder ett format som stöds också samma IRM-skydd som meddelandet. IRM-skydd tillämpas på filer som är associerade med Word, Excel och PowerPoint, samt .xps-filer och bifogade e-postmeddelanden. 
    
- **Administratörer kan använda transportskyddsregler för att tillämpa IRM-skydd automatiskt både Outlook och Outlook på webben.** Du kan skapa transportskyddsregler för IRM-skydda meddelanden. Konfigurera transportskyddsregelåtgärden så att en PRINCIPmall för AD RMS-rättigheter används för meddelanden som uppfyller regelvillkoret. När du har aktivera IRM är organisationens principmallar för AD RMS-rättigheter tillgängliga för användning med transportskyddsregelåtgärden Tillämpa rättighetsskydd **på meddelandet i**.
    
- **Administratörer kan skapa Outlook skyddsregler.** Outlook-skyddsregler tillämpar automatiskt IRM-skydd på meddelanden i Outlook 2010 (inte Outlook på webben) baserat på meddelandevillkor som innehåller avsändarens avdelning, vem meddelandet skickas till och om mottagare finns inom eller utanför organisationen. Mer information finns i [Skapa Outlook skyddsregel.](/exchange/create-an-outlook-protection-rule-exchange-2013-help)
