---
title: Komma igång med hantering av arkivhandlingar i Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Behöver du en lösning för hantering av arkivhandlingar för Microsoft 365 för att hantera värdefullt innehåll för rättsliga, affärsmässiga eller regelmässiga skyldigheter, men är osäker på var du ska börja? Läs några praktiska råd för att komma igång.
ms.openlocfilehash: 0382c1419654e4c1d2c809b3a9c32252fd50f554
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244350"
---
# <a name="get-started-with-records-management"></a>Komma igång med hantering av arkivhandlingar

>*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Är du redo att börja hantera organisationens högt värderade innehåll för rättsliga, affärsmässiga eller regelmässiga skyldigheter genom att använda en lösning för hantering av arkivhandlingar i Microsoft 365? Använd följande anvisningar för att komma igång:

1. **Förstå lösningen för hantering av arkivhandlingar** och vilka åtgärder som tillåts eller blockeras när dokument och e-postmeddelanden är deklarerade arkivhandlingar: [Mer information om hantering av arkivhandlingar](records-management.md). 

2. **Förstå kvarhållningsetiketter och hur kvarhållning fungerar** för SharePoint och Exchange, eftersom kvarhållningsetiketter används för att deklarera arkivhandlingar: [Mer information om kvarhållningsprinciper och kvarhållningsetiketter](retention.md)

3. **Skapa en filplan för kvarhållningsinställningar och åtgärder** genom att [importera en befintlig plan](file-plan-manager.md#import-retention-labels-into-your-file-plan ) om du har en sådan eller skapa [nya kvarhållningsetiketter som deklarerar arkivhandlingar](declare-records.md).

4. **Publicera och använda kvarhållningsetiketter**. Kvarhållningsetiketter är återanvändbara byggblock som kan användas i flera principer och läggas till i användarnas arbetsflöden: 
    
    - [Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)
    - [Använda en kvarhållningsetikett för innehåll automatiskt](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>Prenumerations- och licenskrav för hantering av arkivhandlingar

Det finns flera olika prenumerationer som stöder hantering av arkivhandlingar. Licenskraven för användare beror på vilka funktioner du använder.

Om du vill se licensalternativen för att användarna ska kunna dra nytta av efterlevnadsfunktioner i Microsoft 365 kan du gå till [licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Hantering av arkivhandlingar finns i avsnittet [Hantering av arkivhandlingar](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) och i den relaterade nedladdningsbara PDF- eller Excel-filen för licenskrav på funktionsnivå.

## <a name="permissions-required-for-records-management"></a>Behörigheter som krävs för hantering av arkivhandlingar

Medlemmar i efterlevnadsteamet som ansvarar för hantering av arkivhandlingar behöver behörighet till [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/). Som standard har klientadministratören (global administratör) åtkomst till den här platsen och kan ge ansvariga för uppfyllelse av myndighetskrav och andra personer åtkomst utan att ge dem alla behörigheter en klientadministratör har. För att bevilja behörigheter för den här begränsade administrationen rekommenderar vi att du lägger till användare i administratörsrollgruppen för **hantering av arkivhandlingar**. Då beviljas behörigheter för alla funktioner som hör till hantering av arkivhandlingar, till exempel [borttagningsgranskning och verifiering](disposition.md). 

För skrivskyddade roller kan du skapa en ny rollgrupp och lägga till rollen för **skrivskyddad hantering av arkivhandlingar** i den här gruppen. 

Mer information om rollgrupper och roller finns i [Behörigheter i Säkerhets- och efterlevnadscenter](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Anvisningar om hur du lägger till användare i rollgrupper och tilldelar roller finns i [Ge användare åtkomst till Säkerhets- och efterlevnadscenter](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Dessa behörigheter krävs endast för att skapa, konfigurera och använda kvarhållningsetiketter som deklarerar arkivhandlingar och för att hantera borttagning. Den som konfigurerar etiketterna behöver inte åtkomst till innehållet.

## <a name="common-scenarios-for-records-management"></a>Vanliga scenarier för hantering av arkivhandlingar

Använd följande tabell för att koppla dina verksamhetskrav till scenarier som stöds av hantering av arkivhandlingar.

> [!NOTE]
> Eftersom hantering av arkivhandlingar använder kvarhållningsetiketter för att markera ett objekt som en arkivhandling, tas många scenarier i den här tabellen även upp som [vanliga scenarier för kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels).

|Jag vill ...|Dokumentation|
|----------------|---------------|
|Deklarera en arkivhandling |[Deklarera arkivhandlingar med kvarhållningsetiketter](declare-records.md)|
|Uppdatera en arkivhandling |[Använda versionshantering för arkivhandlingar för att uppdatera arkivhandlingar som lagras i SharePoint eller OneDrive](record-versioning.md)|
|Låta administratörer och användare använda kvarhållnings- och borttagningsåtgärder för dokument och e-postmeddelanden manuellt: <br />– SharePoint <br />– OneDrive <br />– Outlook och Outlook på webben|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Låta webbplatsadministratörer ange standardåtgärder för kvarhållning och borttagning för allt innehåll i ett bibliotek, en mapp eller en dokumentgrupp i SharePoint|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Låta användarna använda kvarhållnings- och borttagningsåtgärder för e-postmeddelanden automatiskt med hjälp av Outlook-regler|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Låta administratörer använda kvarhållnings- och borttagningsåtgärder för en dokumenttolkningsmodell, så att dessa automatiskt tillämpas på identifierade dokument i ett SharePoint-bibliotek|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Automatiskt använda kvarhållnings- och borttagningsåtgärder för dokument och e-postmeddelanden |[Använda en kvarhållningsetikett för innehåll automatiskt](apply-retention-labels-automatically.md)|
|Starta kvarhållningsperioden när en händelse inträffar, till exempel:  <br />– Medarbetare lämnar organisationen <br />– Kontrakt upphör att gälla <br />– Slutet på en produktlivscykel| [Starta kvarhållning när en händelse inträffar](event-driven-retention.md)|
|Begränsa ändringar av principer för att uppfylla regelkrav eller skydda mot otillåtna administratörer| [Använda bevarandelås för att begränsa ändringar av kvarhållningsprinciper och principer för kvarhållningsetiketter](retention-preservation-lock.md)
|Hantera livscykeln för olika dokumenttyper i SharePoint| [Använda kvarhållningsetiketter för att hantera livscykeln för dokument som lagras i SharePoint](auto-apply-retention-labels-scenario.md)|
|Se till att någon granskar och godkänner innan innehållet tas bort i slutet av kvarhållningsperioden|[Borttagningsgranskningar](disposition.md#disposition-reviews) |
|Ha bevis på borttagningen när innehåll tas bort permanent i slutet av kvarhållningsperioden|[Borttagning av arkivhandlingar](disposition.md#disposition-of-records) |
| Övervaka hur och var kvarhållnings- och borttagningsinställningar används för objekt | [Övervaka kvarhållningsetiketter](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>Dokumentation för slutanvändare för arkivhandlingar

Kvarhållningsetiketter som används för hantering av arkivhandlingar har en användargränssnittsnärvaro i Microsoft 365-appar. Se till att du ger vägledning för slutanvändarna och supportavdelningen innan du distribuerar kvarhållningsetiketter i produktionsnätverket.

Om du vill hjälpa användare att använda kvarhållningsetiketter i SharePoint och OneDrive, som innehåller information om hu du kan låsa upp poster för redigering, kan du läsa [Använda kvarhållningsetiketter på filer i SharePoint eller OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

Den mest effektiva dokumentationen för slutanvändare är dock den anpassade vägledningen och anvisningarna som du ger för kvarhållningsetiketternas namn och konfigurationer du väljer. Läs följande blogginlägg som har ett nedladdningspaket som du kan använda för att utbilda användarna och påskynda införandet: [Slutanvändarutbildning för kvarhållningsetiketter i M365 – så här påskyndar du införandet](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).
