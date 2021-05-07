---
title: Översikt över dubbel kryptering och vanliga frågor och svar
description: Vanliga frågor och svar om Dubbelnyckelkryptering för Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162134"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Vanliga frågor och svar om dubbel nyckelkryptering

Har du en fråga om hur Dubbelnyckelkryptering fungerar? Sök efter ett svar här.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Vad är dubbelnyckelkryptering för Microsoft 365 (DKE)?

Dubbel nyckelkryptering för Microsoft 365 kunder kan skydda sina högkänsliga data för att uppfylla specialiserade krav. Det hjälper kunderna att behålla full kontroll över sina krypteringsnycklar. Den använder två nycklar för att skydda data. en tangent i din kontroll och en andra nyckel som lagras säkert i Microsoft Azure. Visning av data skyddade med dubbelnyckelkryptering kräver åtkomst till båda tangenterna. Eftersom Microsoft bara har tillgång till en av dessa nycklar förblir skyddade data otillgängliga för Microsoft, vilket säkerställer att du har full kontroll över din datasekretess och säkerhet.  

Du kan lagra tjänsten dubbelnyckelkryptering som används för att begära din nyckel på valfri plats (lokal nyckelhanteringsserver eller i molnet). Du behåller tjänsten på samma sätt som andra program. Med dubbel nyckelkryptering kan du styra åtkomsten till tjänsten dubbelnyckelkryptering. Du kan lagra känslig information lokalt eller flytta dem till molnet. Du kan vara säker på att förhindra åtkomst från tredje part eftersom du har fullständig kontroll över din nyckel. Med dubbel nyckelkryptering kan du lagra dina data och nyckeln på samma plats.

DKE hjälper dig att uppfylla regelkrav i flera bestämmelser och standarder som General Data Protection Regulation (GDPR), Health Insurance Portability and Accountability Act (HIPAA), Gramm-Leach-Bliley Act (GLBA), Rysslands lagar om data localization – Federal Law No. 242-FZ, Australia's Federal Privacy Act 1988 och New Zealand's Privacy Act 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Kan jag använda dubbelnyckelkryptering med Microsoft Office inbyggda känslighetsetiketter?

Du måste använda den enhetliga etikettklienten för Azure Information Protection för att skydda dokument med Dubbelnyckelkryptering. För närvarande kan du inte använda Microsoft Office inbyggda känslighetsetiketter.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>Vilka Microsoft 365 appar kan jag använda med DKE?

Du kan använda DKE-etiketter för att skydda dokument med skrivbordsversionerna av Word, Excel och PowerPoint på Windows. Kontrollera att du använder *.12711 eller senare (skrivbordsversioner av Word, PowerPoint och Excel) Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Hur skiljer sig dubbelnyckelkryptering från den befintliga lösningen att hålla din egen nyckel (HYOK) kvar?

Dubbel nyckelkryptering krypterar dina data med två nycklar. Krypteringsnyckeln finns i din kontroll och den andra nyckeln lagras i Microsoft Azure, så att du kan flytta krypterade data till molnet. HYOK skyddar innehållet med endast en nyckel och nyckeln finns alltid lokalt.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Kan dubbelnyckelkrypterade dokument delas externt?

Du kan dela dubbelnyckelkrypterade dokument med användare i en separat klientorganisation så länge dessa användare:

- Ha den behörighet som krävs för att komma åt din nyckel i tjänsten dubbelnyckelkryptering.

- Ha den behörighet som krävs för att komma åt din nyckel i Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>Vad händer med dokument som skyddas med HYOK?

Distribution av dubbelnyckelkryptering påverkar inte din befintliga HYOK-konfiguration. Vi rekommenderar dock att du börjar använda dubbelnyckelkryptering parallellt med HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Kan jag köra Dubbelnyckelkryptering i min icke-Microsoft-luftig miljö?

DKE stöder inte dessa miljöer eftersom tjänsten kräver åtkomst till Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Var kan jag lagra krypterade dubbelnyckeldokument?

Du kan lagra krypterade dubbelnyckeldokument lokalt eller i molnet. I molnet kan du flytta krypterat innehåll till SharePoint Online och OneDrive för företag. Eftersom Microsoft inte har tillgång till din privata nyckel är de krypterade data ogenomskinliga för Microsoft. Det innebär också att du inte kan visa krypterade dokument online i Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>Vilka regioner och språk finns dubbel nyckelkryptering tillgängligt i? Finns Dubbelnyckelkryptering tillgängligt över hela världen?

DKE-etiketter lokaliseras till samma språk som andra känslighetsetiketter i Microsoft Information Protection. Dubbelnyckelkryptering är tillgängligt i hela världen.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>Kan jag konvertera en etikett som inte är en DKE till en DKE-etikett?

Nej. Du kan inte lägga till DKE på en etikett när du har skapat den. I stället måste du välja **Använd dubbelnyckelkryptering** och ange URL-adressen till tjänsten för dubbelnyckelkryptering när du skapar etiketten.

## <a name="how-do-i-roll-my-dke-keys"></a>Hur rullar jag mina DKE-tangenter?

Instruktioner om hur du rullar (kallas även att rotera eller nyckela om) nyckeln du lagrar i Azure finns i Åtgärder för Azure [Information Protection-klientnyckeln.](/azure/information-protection/operations-customer-managed-tenant-key)

Mer [information om hur du skapar](double-key-encryption.md#tenant-and-key-settings) en ny nyckel för DKE-tjänsten finns i Inställningar för klientorganisation och nyckel.

När du skapar en nyckel kan du konfigurera ett namn och en GUID. Om du sedan roterar en nyckel behåller du den gamla posten med namnet och GUID men lägger till en ny post med samma namn men olika GUID. Den nya nyckeln anges som aktiv så att den offentliga nyckelns API börjar returnera den för ny kryptering. Båda nycklarna går att dekryptera, vilket innebär att nytt och gammalt innehåll kan dekrypteras.