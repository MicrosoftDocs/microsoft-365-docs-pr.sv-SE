---
title: Avancerad meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Avancerad meddelandekryptering hjälper organisationer att uppfylla sina efterlevnadsskyldigheter genom att administratörer kan göra ännu mer med skyddade meddelanden.
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162198"
---
# <a name="advanced-message-encryption"></a>Avancerad meddelandekryptering

Office 365 Advanced Message Encryption ingår i [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (priser för ideella föreningar), Office 365 Enterprise E5 (priser för ideella föreningar) och Office 365 Education A5. Om din organisation har en prenumeration som inte inkluderar Office 365 Advanced Message Encryption Kan du köpa det med SKU-tillägget Microsoft 365 E5 Compliance för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar) eller Office 365 Advanced Compliance SKU-tillägget för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar), Office 365-SKU:er eller SKU-tillägget Microsoft 365 E5/A5 för informationsskydd och styrning för Microsoft 365 A3/E3.

Avancerad meddelandekryptering hjälper kunder att uppfylla efterlevnadsskyldigheter som kräver mer flexibla kontroller över externa mottagare och deras åtkomst till krypterade e-postmeddelanden. Med Avancerad meddelandekryptering i Office 365 kan du styra vilka känsliga e-postmeddelanden som delas utanför organisationen med automatiska principer. Du konfigurerar de här principerna för att identifiera känsliga informationstyper som PII, finans- och hälso-ID, eller så kan du använda nyckelord för att förbättra skyddet. När du har konfigurerat principerna kopplar du principer med anpassade e-postmallar och lägger sedan till ett utgångsdatum för att få bättre kontroll över e-postmeddelanden som passar principen. Dessutom kan administratörer ytterligare kontrollera krypterade e-postmeddelanden som nås externt via en säker webbportal genom att återkalla åtkomsten till e-postmeddelandet när som helst.

Du kan bara återkalla och ange ett utgångsdatum för e-postmeddelanden som skickas till externa mottagare.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Komma igång med Office 365 Advanced Message Encryption

I följande artiklar beskrivs hur du kryptering och användning av avancerad meddelandekryptering.

Organisationen måste ha en prenumeration som omfattar alla Office 365 Advanced Message Encryption. Detaljerad information om prenumerationer som stöds finns i [beskrivningen av meddelandepolicyn och efterlevnadstjänsten.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

Om du inte redan Meddelandekryptering i Office 365 kan du [gå till Konfigurera Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md)

Med Avancerad meddelandekryptering är du inte begränsad till en enda varumärkesmall. I stället kan du skapa och använda flera varumärkesmallar. Mer information finns i [Lägga till företagets varumärke i krypterade meddelanden.](add-your-organization-brand-to-encrypted-messages.md)

[Ange ett utgångsdatum för e-post som krypteras med Office 365 Advanced Message Encryption](ome-advanced-expiration.md). Kontrollera känsliga e-postmeddelanden som delas utanför organisationen med automatiska principer som förbättrar skyddet genom att åtkomsten till krypterade e-postmeddelanden upphör att gälla via en säker webbportal.

[Återkalla e-post som krypteras med Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md). Kontrollera känsliga e-postmeddelanden som delas utanför organisationen och skydda dem genom att återkalla åtkomsten via en säker webbportal till krypterade e-postmeddelanden.  

När Office 365 Advanced Message Encryption använder en anpassad varumärkesmall använder Microsoft en figursättning för e-post som passar e-postflödesregeln som du använder mallen för. Du kan bara återkalla meddelanden och tillämpa utgångsdatum för meddelanden som användare får via portalen. Med andra ord e-post där en anpassad varumärkesmall används. Mer information och ett exempel finns i vägledningen i Se till att alla externa mottagare använder [OME-portalen för att läsa krypterad e-post.](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)