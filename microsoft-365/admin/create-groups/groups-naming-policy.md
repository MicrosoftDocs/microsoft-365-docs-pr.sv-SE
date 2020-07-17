---
title: Namngivningspolicy för grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Lär dig hur du skapar en namngivningsprincip för Microsoft 365-grupper.
ms.openlocfilehash: ae216d0d8f3319e9633d300d785b4a8c31702798
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702554"
---
# <a name="groups-naming-policy"></a>Namngivningspolicy för grupper

Du använder en gruppnamnprincip för att tillämpa en konsekvent namngivningsstrategi för grupper som skapats av användare i organisationen. En namngivningsprincip kan hjälpa dig och dina användare att identifiera funktionen för gruppen, medlemskap, geografisk region eller vem som skapade gruppen. Namngivningsprincipen kan också hjälpa till att kategorisera grupper i adressboken. Du kan använda principen för att blockera specifika ord från att användas i gruppnamn och alias.

Namngivningsprincipen tillämpas på grupper som skapas i alla grupparbetsbelastningar (som Outlook, Microsoft Teams, SharePoint, Planner, Yammer osv.). Den tillämpas på både gruppnamnet och gruppaliaset. Den tillämpas när en användare skapar en grupp och när gruppnamn eller alias redigeras för en befintlig grupp.

> [!TIP]
> En namngivningsprincip för Microsoft 365-gruppen gäller endast Microsoft 365-grupper. Det gäller inte distributionsgrupper som skapats i Exchange Online. Om du vill skapa en namngivningsprincip för distributionsgrupper finns i [Skapa en namngivningsprincip för distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

Namnprincipen för grupp består av följande funktioner:

- **Namngivningsprincipen prefix-Suffix**: Du kan använda prefix eller suffix för att definiera namngivningskonventionen för grupper (till exempel:"US \_ My Group \_ Engineering"). Prefix och suffix kan antingen vara fasta strängar eller användarattribut som [Department], som ersätts utifrån den användare som skapar gruppen.

- **Anpassade blockerade ord:** Du kan ladda upp en uppsättning blockerade ord som är specifika för din organisation och som skulle blockeras i grupper som skapats av användare. (Till exempel: "VD, Lön, HR").

## <a name="licensing-requirements"></a>Licenskrav

Om du använder Azure AD-namngivningsprincip för Microsoft 365-grupper krävs att du har men inte nödvändigtvis tilldela en Azure Active Directory Premium P1-licens eller Azure AD Basic EDU-licens för varje unik användare (inklusive gäster) som är medlem i en eller flera Microsoft 365-grupper.

Detta krävs också för administratören som skapar namngivningsprincipen Grupper.

## <a name="prefix-suffix-naming-policy"></a>Namngivningsprincip för Prefix-Suffix

Prefix och suffix kan antingen vara fasta strängar eller användarattribut.

### <a name="fixed-strings"></a>Fasta strängar

Du kan använda korta strängar som kan hjälpa dig att skilja grupper i GAL och vänster navigering av grupparbetsbelastningar. Några av de vanliga suffixen prefix är nyckelord som "Grp \_ Name", ' \# Name', ' \_ Name'

### <a name="attributes"></a>Attribut

Du kan använda attribut som kan hjälpa till att identifiera vem som skapade gruppen som [Avdelning] och var den skapades från som [Land].

|||
|:-----|:-----|
|**Exempel**|Princip = "GRP [GroupName] [Department]"|
||Användarens avdelning = Teknik|
||Skapat gruppnamn = "GRP Min grupp Teknik"|

Azure Active Directory-attribut (Azure AD) stöds är [Avdelning], [Företag], [Office], [StateOrProvince], [CountryOrRegion] och [Titel].

- Användarattribut som inte stöds betraktas som fasta strängar, t.ex. "[postalCode]"

- Tilläggsattribut och egna attribut stöds inte.

Vi rekommenderar att du använder attribut som har värden ifyllda för alla användare i organisationen samt att du inte använder attribut som har långa värden.

### <a name="things-to-look-out-for"></a>Saker att hålla utkik efter

- När du skapar principen är den totala stränglängden för prefix och suffix begränsad till 53 tecken.

- Prefix och suffix får innehålla specialtecken som stöds i gruppens namn och gruppalias. När prefixen och suffixen innehåller specialtecken som inte är tillåtna i gruppaliaset, tillämpas de bara på gruppnamnet. I det här fallet skiljer sig de prefix och suffix som tillämpas på gruppnamnet från dem som tillämpas på gruppaliaset.

  > [!NOTE]
  > En period (.) eller ett bindestreck (-) tillåts var som helst i gruppnamnet, utom i början eller slutet av namnet. Ett understreck (_) tillåts var som helst i gruppnamnet, inklusive i början eller slutet av namnet.

- Om du använder Yammer Microsoft 365-anslutna grupper undviker du att använda följande tecken i namnprincipen: @, \# , \[ , , \] \<, and \> . Om dessa tecken finns i namngivningsprincipen kan vanliga Yammer-användare inte skapa grupper.

## <a name="custom-blocked-words"></a>Anpassade blockerade ord

Du kan ange en kommaavgränsad lista med blockerade ord som ska blockeras i gruppnamn och alias.

Inga substrängsökningar utförs. Närmare bestämt krävs en exakt matchning mellan användarens angivna namn och de anpassade blockerade orden för att utlösa ett fel. Sub-string sökning görs inte så att användarna kan använda några av de vanligaste orden som "Klass" även om "ass" är ett blockerat ord.

**Saker att hålla utkik efter:**

- Blockerade ord är inte skiftlägeskänsliga.

- Om en användare anger ett blockerat ord visas ett felmeddelande med det blockerade ordet i gruppklienten.

- Det finns inga teckenbegränsningar för de blockerade ord som används.

- Det finns en gräns på 5000 ord som kan ställas in som blockerade ord.

## <a name="admin-override"></a>Åsidosättning för administratör

Vissa administratörer är undantagna från de här principerna i alla grupparbetslaster och slutpunkter så att de kan skapa grupper med blockerade ord och med de namnkonventioner de önskar. Nedan följer listan över administratörsroller som är undantagna från namnprincipen för grupp.

- Global administratör

- Partner Tier1-support

- Partner Tier2-support

- Användarkontoadministratör

- Katalogredigerare

## <a name="how-to-set-up-the-naming-policy"></a>Så här ställer du in namngivningsprincipen

Så här ställer du in en namngivningsprincip:

1. Klicka på **Grupper**under **Hantera**i [Azure Active Directory](https://aad.portal.azure.com).
2. Klicka på **Namngivningsprincip**under **Inställningar.**
3. Välj fliken **Gruppnamnprincip.**
4. Under **Aktuell princip**väljer du om du vill kräva ett prefix eller suffix eller båda och markerar lämpliga kryssrutor.
5. Välj mellan **Attribut** och **Sträng** för varje rad och ange sedan attributet eller strängen.
6. När du har lagt till de prefix och suffix som du behöver klickar du på **Spara**.

![Skärmbild av principinställningarna för grupper i Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> StaffHub-team följer inte namngivningsprincipen, men den underliggande Microsoft 365-gruppen gör det. Prefix och suffix används inte för StaffHub-gruppnamn, och egna blockerade ord kontrolleras inte. Men StaffHub tillämpar prefix och suffix och tar bort blockerade ord från den underliggande Microsoft 365-gruppen.

## <a name="more-articles-on-naming-policy"></a>Fler artiklar om namngivningsprincip

[Framtvinga en namngivningsprincip för Microsoft 365-grupper i Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)

[Azure Active Directory-cmdletar för att konfigurera gruppinställningar](https://go.microsoft.com/fwlink/?linkid=868341)
