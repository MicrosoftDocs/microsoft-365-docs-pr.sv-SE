---
title: Komma igång med kvarhållningsprinciper och kvarhållningsetiketter
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Är du redo att börja implementera kvarhållningsprinciper och kvarhållningsetiketter som styr organisationens data, men är osäker på var du ska börja? Läs några praktiska riktlinjer för att komma igång.
ms.openlocfilehash: bd3ed5e354ee80831cb1af073b6da6f277418b51
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689043"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Komma igång med kvarhållningsprinciper och kvarhållningsetiketter

>*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Är du redo att börja styra organisationens data genom att behålla det innehåll som du behöver och ta bort innehåll som du inte behöver? Använd följande riktlinjer för att komma igång:

1. **Förstå hur kvarhållning fungerar** i Microsoft 365 och undersök sedan om du behöver använda kvarhållningsprinciper eller kvarhållningsetiketter, eller en kombination: [Mer information om kvarhållning](retention.md)

2. **Identifiera de kvarhållningsinställningar och åtgärder** som krävs av organisationens principer eller branschföreskrifter.
    
    Som ett led i utvärderingen bestämmer du om du ska använda [hantering av arkivhandlingar](records-management.md).

3. **Skapa kvarhållningsprinciper och kvarhållningsetiketter** baserat på de kvarhållningsinställningar och åtgärder som du har identifierat.
    
    För kvarhållningsetiketter kan det vara bra att använda en [filplan](file-plan-manager.md) till att definiera och förfina kvarhållningsetiketterna i ett kalkylblad. Importera sedan kalkylbladet för att skapa etiketterna.
    
3. **Publicera och använda kvarhållningsetiketter**. Även om kvarhållningsprinciper är utformade att konfigureras och sedan glömmas bort, är kvarhållningsetiketter återanvändbara byggblock som kan användas i flera principer och kan ingå i användararbetsflöden. Se en lista med [vanliga scenarier](#common-scenarios-for-retention-policies-and-retention-labels) som hjälper dig att se hur kvarhållningsetiketter kan användas. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Prenumerations- och licenskrav för kvarhållningsprinciper och kvarhållningsetiketter

Flera olika prenumerationer stöder kvarhållningsprinciper och kvarhållningsetiketter och licenskraven för användarna beror på de funktioner som du använder.

Om du vill se licensalternativen för att användarna ska kunna dra nytta av efterlevnadsfunktioner i Microsoft 365 kan du gå till [licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Kvarhållning beskrivs i avsnittet [Informationsstyrning](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) och i den relaterade nedladdningsbara PDF- eller Excel-filen för licenskrav på funktionsnivå.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Behörigheter som krävs för att skapa och hantera kvarhållningsprinciper och kvarhållningsetiketter

Medlemmar i efterlevnadsteamet som skapar och hanterar kvarhållningsprinciper och kvarhållningsetiketter måste ha behörighet till [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/). Som standard har klientadministratören (global administratör) åtkomst till platsen och kan ge efterlevnadsansvariga och andra personer åtkomst utan att ge dem alla behörigheter som en klientadministratör har. För att bevilja behörigheter för begränsad administration rekommenderar vi att du lägger till användarna i administratörsrollgruppen **Efterlevnadsadministratör**.

Du kan också skapa en ny rollgrupp och lägga till rollen **Kvarhållningshantering** i gruppen i stället för att använda standardrollen. Om du vill ha en skrivskyddad roll använder du **Skrivskyddad kvarhållningshantering**. 

Mer information om rollgrupper och roller finns i [Behörigheter i Säkerhets- och efterlevnadscenter](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Anvisningar om hur du lägger till användare i rollgrupper och tilldelar roller finns i [Ge användare åtkomst till Säkerhets- och efterlevnadscenter](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Dessa behörigheter krävs endast för att skapa, konfigurera och använda kvarhållningsprinciper och kvarhållningsetiketter. Den som konfigurerar principerna och etiketterna behöver inte ha åtkomst till innehållet.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Vanliga scenarier för kvarhållningsprinciper och kvarhållningsetiketter

Använd följande tabell för att mappa dina verksamhetskrav till kvarhållningsscenarier som stöds av kvarhållningsprinciper och kvarhållningsetiketter.

|Jag vill ...|Dokumentation|
|----------------|---------------|
|Ange kvarhållnings- och borttagningsåtgärder med Microsoft 365-tjänsten på ett effektivt sätt: <br />-  Exchange  <br />- SharePoint  <br />– OneDrive  <br />- Microsoft 365-grupper <br />- Skype för företag  <br />- Microsoft Teams <br />- Yammer-nätverk |[Skapa och konfigurera kvarhållningsprinciper](create-retention-policies.md)|
|Låta administratörer och användare använda kvarhållnings- och borttagningsåtgärder för dokument och e-postmeddelanden manuellt: <br />– SharePoint <br />– OneDrive <br />– Outlook och Outlook på webben|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Låta webbplatsadministratörer ange standardåtgärder för kvarhållning och borttagning för allt innehåll i ett bibliotek, en mapp eller en dokumentgrupp i SharePoint|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Låta användarna använda kvarhållnings- och borttagningsåtgärder för e-postmeddelanden automatiskt med hjälp av Outlook-regler|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Låta administratörer använda kvarhållnings- och borttagningsåtgärder för en dokumenttolkningsmodell, så att dessa automatiskt tillämpas på identifierade dokument i ett SharePoint-bibliotek|[Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)|
|Automatiskt använda kvarhållnings- och borttagningsåtgärder för dokument och e-postmeddelanden |[Använda en kvarhållningsetikett för innehåll automatiskt](apply-retention-labels-automatically.md)|
|Starta kvarhållningsperioden när en händelse inträffar, till exempel:  <br />– Medarbetare lämnar organisationen <br />– Kontrakt upphör att gälla <br />– Slutet på en produktlivscykel| [Starta kvarhållning när en händelse inträffar](event-driven-retention.md)|
|Begränsa ändringar av principer för att uppfylla regelkrav eller skydda mot otillåtna administratörer| [Använda bevarandelås för att begränsa ändringar av kvarhållningsprinciper och principer för kvarhållningsetiketter](retention-preservation-lock.md)
|Se till att någon granskar och godkänner innan innehållet tas bort i slutet av kvarhållningsperioden|[Borttagningsgranskningar](disposition.md#disposition-reviews) |
| Övervaka hur och var kvarhållnings- och borttagningsinställningar används för objekt | [Övervaka kvarhållningsetiketter](retention.md#monitoring-retention-labels) |
|Använda en enskild lösning för hantering av arkivhandlingar för dokument och e-postmeddelanden |[Mer information om hantering av arkivhandlingar](records-management.md) |

Om du använder kvarhållningsetiketter vid hantering av arkivhandlingar finns det ytterligare scenarier som är unika för kvarhållningsetiketter som markerar innehåll som en post. Se [Vanliga scenarier för hantering av arkivhandlingar](get-started-with-records-management.md#common-scenarios-for-records-management).

## <a name="end-user-documentation-for-retention"></a>Slutanvändardokumentation vid kvarhållning

De flesta kvarhållningsprinciperna fungerar utan att användaren interagerar med bakgrunden och användarna behöver därför inte särskilt mycket dokumentation. Kvarhållningsprinciperna för Teams informerar användarna när deras meddelanden har tagits bort med en länk till [Teams-meddelanden om kvarhållningsprinciper](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

Eftersom kvarhållningsetiketter har en gränssnittsnärvaro i Microsoft 365-appar bör du ge vägledning till slutanvändarna och supportavdelningen innan du distribuerar etiketterna till produktionsnätverket. Om du vill hjälpa användare att använda kvarhållningsetiketter i SharePoint och OneDrive kan du läsa [Använda kvarhållningsetiketter på filer i SharePoint eller OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

Den mest effektiva dokumentationen för slutanvändare är dock den anpassade vägledningen och anvisningarna som du ger för kvarhållningsetiketternas namn och konfigurationer du väljer. Se följande sida och nedladdningar som du kan använda för att utbilda dina användare: [Utbildning för slutanvändare för kvarhållningsetiketter](https://microsoft.github.io/ComplianceCxE/enduser/retention/).