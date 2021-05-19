---
title: Microsoft 365 namnprincip för grupper
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
recommendations: false
description: Lär dig hur du skapar en namnprincip för Microsoft 365 grupper.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538177"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 namnprincip för grupper

Du kan använda en gruppnamnprincip för att tillämpa en konsekvent namngivningsstrategi för grupper som skapas av användare i organisationen. En namnprincip kan hjälpa dig och dina användare att identifiera funktionen för gruppen, medlemskap, geografiskt område eller vem som skapade gruppen. Namnprincipen kan även hjälpa till att kategorisera grupper i adressboken. Du kan använda principen för att blockera specifika ord från att användas i gruppnamn och gruppalias.

Namnprincipen tillämpas på grupper som skapas i alla grupparbetsbelastningar (t.ex. Outlook, Microsoft Teams, SharePoint, Planner Yammer osv.). Det används för både gruppnamn och gruppalias. Det används också när en användare skapar en grupp och när gruppens namn, alias, beskrivning eller avatar redigeras för en befintlig grupp.

> [!TIP]
> En Microsoft 365 för gruppnamn gäller endast för Microsoft 365 grupper. Den gäller inte distributionsgrupper som skapats i Exchange Online. Information om hur du skapar en namnprincip för distributionsgrupper finns [i Skapa en namngivningsprincip för distributionsgrupp.](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)

Namnprincipen för grupp består av följande funktioner:

- **Prefix-Suffixnamnprincip:** Du kan använda prefix eller suffix för att definiera namngivningskonventioner för grupper (till exempel "Us \_ My Group \_ Engineering"). Prefix och suffix kan antingen vara fasta strängar eller användarattribut som [Department], som ersätts utifrån den användare som skapar gruppen.

- **Egna blockerade ord:** Du kan ladda upp en uppsättning blockerade ord som är specifika för din organisation och som blockeras i grupper som skapats av användare. (Till exempel: "VD, Löneavdelningen, HR").

## <a name="licensing-requirements"></a>Licensieringskrav

Om du använder Azure AD-namnprincip för Microsoft 365 Grupper kräver det att du har, men inte nödvändigtvis tilldelar en Azure Active Directory Premium P1-licens eller Azure AD Basic EDU-licens för varje unik användare (inklusive gäster) som är medlem i en eller flera Microsoft 365-grupper.

Det här krävs också för administratören som skapar namnprincipen för grupper.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix namnprincip

Prefix och suffix kan antingen vara fasta strängar eller användarattribut.

### <a name="fixed-strings"></a>Fasta strängar

Du kan använda korta strängar som hjälper dig att skilja mellan grupper i GAL och vänster navigering i gruppens arbetslaster. Några vanliga prefix/suffix är nyckelord som \_ "Grp-namn", \# "Namn", " \_ Namn"

### <a name="attributes"></a>Attribut

Du kan använda attribut som kan hjälpa dig identifiera vem som skapade gruppen, till exempel [Department], och var den skapades, som [Land].

Exempel:

- Princip = "GRP [GroupName] [Department]"
- Användarens avdelning = Teknik
- Skapat gruppnamn = "GRP Min grupp Teknik"

Azure AD-attribut som stöds Azure Active Directory [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] och [Title].

- Användarattribut som inte stöds betraktas som fasta strängar, till exempel [postalCode].

- Tilläggsattribut och egna attribut stöds inte.

Vi rekommenderar att du använder attribut som har värden ifyllda för alla användare i organisationen samt att du inte använder attribut som har långa värden.

### <a name="things-to-look-out-for"></a>Saker att vara ute efter

- När du skapar principen är den totala stränglängden för prefix och suffix begränsad till 53 tecken.

- Prefix och suffix får innehålla specialtecken som stöds i gruppens namn och gruppalias. Om prefix och suffix innehåller specialtecken som inte är tillåtna i gruppaliaset tillämpas de bara på gruppnamnet. I det här fallet skiljer sig de prefix och suffix som tillämpas på gruppnamnet från dem som tillämpas på gruppaliaset.

  > [!NOTE]
  > En punkt (.) eller ett bindestreck (-) tillåts någonstans i gruppnamnet, förutom i början eller slutet av namnet. Ett understreck (_) tillåts var som helst i gruppnamnet, även i början eller slutet av namnet.

- Om du använder Yammer Office 365 ska du undvika att använda följande tecken i namnprincipen: @, \# , \[ , , \] \<, and \> . Om dessa tecken ingår i namnprincipen kan Yammer användare inte skapa grupper.

> [!Tip]
> - Använd korta strängar som suffix.
> - Använd attribut med värden.
> - Var inte för kreativ, den totala namnlängden får vara högst 264 tecken.
> - Upload organisationens specifika blockerade ord för att begränsa användning.

## <a name="custom-blocked-words"></a>Egna blockerade ord

Du kan ange en kommaavgränsad lista med blockerade ord som ska blockeras i gruppnamn och gruppalias.

Ingen sökning utförs i understrängar. mer specifikt krävs en exakt matchning mellan det angivna namnet och de egna blockerade orden för att ett fel ska utlösas.

**Saker att hålla reda på:**

- Blockerade ord är inte skiftlägeskänsliga.

- Om en användare anger ett blockerat ord visas ett felmeddelande med det blockerade ordet i gruppklienten.

- Det finns inga teckenbegränsningar för de blockerade ord som används.

- Det finns en gräns på 5 000 ord som kan anges som blockerade ord.

## <a name="admin-override"></a>Åsidosättning för administratör

Vissa administratörer är undantagna från dessa principer i alla grupparbetsbelastningar och slutpunkter så att de kan skapa grupper med blockerade ord och med de namnkonventioner de önskar. Nedan följer listan över administratörsroller som är undantagna från namnprincipen för grupp.

- Global administratör

- Partner Tier1-support

- Partner Tier2-support

- Användarkontoadministratör

## <a name="how-to-set-up-the-naming-policy"></a>Så här ställer du in namnprincipen

Så här ställer du in en namnprincip:

1. I [Azure Active Directory](https://aad.portal.azure.com)under **Hantera klickar** du på **Grupper.**
2. Klicka **Inställningar** namnprincip under **Namnprincip.**
3. Välj fliken **Gruppnamnprincip.**
4. Under **Aktuell princip** väljer du om du vill kräva prefix eller suffix eller båda. Markera sedan lämpliga kryssrutor.
5. Välj mellan **Attribut** och **Sträng** för varje rad och ange sedan attributet eller strängen.
6. När du har lagt till de prefix och suffix du behöver klickar du på **Spara.**

![Skärmbild av namnprincipinställningarna för grupper i Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Azure Active Directory cmdlets för att konfigurera gruppinställningar](/azure/active-directory/enterprise-users/groups-settings-cmdlets)