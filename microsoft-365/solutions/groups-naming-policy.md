---
title: Microsoft 365 grupper namn princip
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Lär dig hur du skapar en namn princip för Microsoft 365 Groups.
ms.openlocfilehash: 55faf5c61d577b35b34923efc7b65457fe46de29
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377611"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 grupper namn princip

Du kan använda en princip för att skapa en konsekvent namn strategi för grupper som skapas av användare i organisationen. En namn princip hjälper dig och dina användare att identifiera funktionen för gruppen, medlemskap, geografiska områden eller vem som skapat gruppen. Namn princip kan också hjälpa kategorisering av grupper i adress boken. Du kan använda principen för att blockera specifika ord från att användas i grupp namn och alias.

Namngivnings principen tillämpas på grupper som skapas i alla grupp arbets uppgifter (som Outlook, Microsoft Teams, SharePoint, Planner, Yammer osv.). Den används för både grupp namn och gruppalias. Den används när en användare skapar en grupp och när grupp namn eller alias redige ras för en befintlig grupp.

> [!TIP]
> En Microsoft 365-grupp för namngivnings princip gäller endast för Microsoft 365-grupper. Det gäller inte distributions grupper som har skapats i Exchange Online. Information om hur du skapar en namngivnings princip för distributions grupper finns i [skapa en namn princip för en distributions grupp](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

Namnprincipen för grupp består av följande funktioner:

- **Prefix – namngivnings princip för suffix**: du kan ange namn konvention för grupper (till exempel: " \_ min grupp \_ teknik"). Prefix och suffix kan antingen vara fasta strängar eller användarattribut som [Department], som ersätts utifrån den användare som skapar gruppen.

- **Anpassade blockerade ord**: du kan ladda upp en uppsättning blockerade ord som är specifika för din organisation som blockeras i grupper som skapats av användare. (Till exempel: "VD, lön, HR").

## <a name="licensing-requirements"></a>Licens krav

För att använda Azure AD-grupprinciper för Microsoft 365-grupper måste du ha, men inte nödvändigt vis, en Azure Active Directory Premium P1-licens eller Azure AD Basic EDU-licens för varje enskild användare (inklusive gäster) som är medlem i en eller flera Microsoft 365-grupper.

Det här är också obligatoriskt för administratören som skapar namn princip för grupper.

## <a name="prefix-suffix-naming-policy"></a>Prefix – namngivnings princip för suffix

Prefix och suffix kan antingen vara fasta strängar eller användarattribut.

### <a name="fixed-strings"></a>Fasta strängar

Du kan använda korta strängar som hjälper dig att skilja grupper i det GAL och vänstra navigerings fältet i gruppens arbets belastning. Vissa vanliga prefix är nyckelord som "GRP \_ Name", " \# namn", " \_ namn"

### <a name="attributes"></a>Attribut

Du kan använda attribut som hjälper dig att identifiera vem som skapade gruppen, till exempel [avdelning] och var den skapades från gilla [Country].

Exempel:

- Princip = "GRP [GroupName] [Department]"
- Användarens avdelning = Teknik
- Skapat gruppnamn = "GRP Min grupp Teknik"

Azure Active Directory (Azure AD)-attribut som stöds är [avdelning], [företag], [Office], [StateOrProvince], [CountryOrRegion] och [title].

- Användarattribut som inte stöds betraktas som fasta strängar, till exempel [post nummer].

- Tilläggsattribut och egna attribut stöds inte.

Vi rekommenderar att du använder attribut som har värden ifyllda för alla användare i organisationen samt att du inte använder attribut som har långa värden.

### <a name="things-to-look-out-for"></a>Saker att se ut för

- När du skapar principen är den totala stränglängden för prefix och suffix begränsad till 53 tecken.

- Prefix och suffix får innehålla specialtecken som stöds i gruppens namn och gruppalias. När prefix och suffix innehåller specialtecken som inte är tillåtna i gruppaliaset tillämpas de bara på grupp namnet. I det här fallet skiljer sig de prefix och suffix som tillämpas på gruppnamnet från dem som tillämpas på gruppaliaset.

  > [!NOTE]
  > En punkt (.) eller ett bindestreck (-) tillåts var som helst i grupp namnet, förutom i början eller slutet av namnet. Ett under streck (_) tillåts var som helst i grupp namnet, inklusive i början eller slutet av namnet.

- Om du använder Yammer Office 365-anslutna grupper kan du undvika att använda följande tecken i din namn princip: @, \# , \[ , \] , \<, and \> . Om dessa tecken finns i namn principen kan vanliga Yammer-användare inte skapa grupper.

> [!Tip]
> - Använd korta strängar som suffix.
> - Använd attribut med värden.
> - Är inte för kreativ, total namn längd får högst innehålla 264 tecken.
> - Ladda upp dina organisatoriska blockerade ord för att begränsa användningen.

## <a name="custom-blocked-words"></a>Anpassade blockerade ord

Du kan ange en kommaseparerad lista över blockerade ord som ska blockeras i grupp namn och alias.

Inga under Strängs sökningar utförs; specifikt krävs en exakt matchning mellan den användare som angavs och de anpassade blockerade orden för att utlösa ett fel.

**Saker att se ut för**:

- Blockerade ord är inte skiftlägeskänsliga.

- Om en användare anger ett blockerat ord visas ett felmeddelande med det blockerade ordet i gruppklienten.

- Det finns inga teckenbegränsningar för de blockerade ord som används.

- Det finns en begränsning på 5000 ord som kan anges som blockerade ord.

## <a name="admin-override"></a>Åsidosättning för administratör

Vissa administratörer undantas från dessa principer, i alla grupp arbets belastningar och slut punkter, så att de kan skapa grupper med dessa blockerade ord och deras namngivnings regler. Nedan följer listan över administratörsroller som är undantagna från namnprincipen för grupp.

- Global administratör

- Partner Tier1-support

- Partner Tier2-support

- Användarkontoadministratör

- Katalogredigerare

## <a name="how-to-set-up-the-naming-policy"></a>Så här konfigurerar du namn principen

Så här skapar du en namngivnings princip:

1. Klicka på **grupper**under **Hantera**i [Azure Active Directory](https://aad.portal.azure.com).
2. Klicka på **namn princip**under **Inställningar**.
3. Välj fliken för att **namnge principer** .
4. Under **aktuell princip**väljer du om du vill kräva ett prefix eller ett suffix eller bådadera och markerar lämpliga kryss rutor.
5. Välj mellan **attribut** och **sträng** för varje rad och ange sedan ett attribut eller en sträng.
6. När du har lagt till de prefix och suffix du behöver klickar du på **Spara**.

![Skärm bild av inställningarna för namngivnings princip för grupper i Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Relaterade ämnen

[Azure Active Directory-cmdlets för konfiguration av grupp inställningar](https://go.microsoft.com/fwlink/?linkid=868341)
