---
title: Hantera principer för informationsbarriärer
description: Lär dig hur du redigerar eller tar bort principer för informationsbarriärer.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.openlocfilehash: 668ca8e26371d80f068c2723357ce3ee407db03a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162205"
---
# <a name="manage-information-barrier-policies"></a>Hantera principer för informationsbarriärer

När du har [definierat principer för informationsbarriärer](information-barriers-policies.md)kan du behöva ändra dessa principer eller i dina användarsegment, som en del av [felsökning](information-barriers-troubleshooting.md) eller som vanligt underhåll. Använd den här artikeln som en guide.

## <a name="what-do-you-want-to-do"></a>Vad vill du göra?

|**Åtgärd**|**Beskrivning**|
|:---------|:--------------|
| [Redigera användarkontoattribut](#edit-user-account-attributes) | Fyll i attribut i Azure Active Directory som kan användas för att definiera segment.<br/>Redigera användarkontoattribut när användarna inte ingår i segment bör de vara, ändra vilka segment användarna finns i eller definiera segment med olika attribut. |
| [Redigera ett segment](#edit-a-segment) | Redigera segment när du vill ändra hur ett segment definieras. <br/>Du kanske till exempel har ursprungligen definierat segment med Hjälp av *Avdelning* och nu vill använda ett annat attribut, till exempel *MemberOf*. |
| [Redigera en princip](#edit-a-policy) | Redigera en princip för informationsbarriärer när du vill ändra hur en princip fungerar.<br/>I stället för att blockera kommunikationen mellan två segment kanske du vill tillåta att kommunikationen bara sker mellan vissa segment. |
| [Ange inaktiv status för en princip](#set-a-policy-to-inactive-status) |Ange en princip som inaktiv status när du vill göra ändringar i en princip eller när du inte vill att en princip ska gälla. |
| [Ta bort en princip](#remove-a-policy) | Ta bort en princip om informationsbarriärer när du inte längre behöver en viss princip. |
| [Stoppa ett principprogram](#stop-a-policy-application) | Vidta den här åtgärden när du vill stoppa processen att tillämpa informationsbarriärprinciper.<br/> Det är inte direkt att stoppa ett principprogram och det ångrar inte principer som redan har tillämpats för användare. |
| [Definiera principer för informationsbarriärer](information-barriers-policies.md) | Definiera en princip för informationsbarriärer när du inte redan har sådana principer, och du måste begränsa kommunikationen mellan specifika grupper av användare. |
| [Felsökning av informationsbarriärer](information-barriers-troubleshooting.md) | Läs den här artikeln om du har oväntade problem med informationsbarriärer. |

> [!IMPORTANT]
> För att utföra de uppgifter som beskrivs i den här artikeln måste du ha tilldelats en lämplig roll, till exempel något av följande:<br/>- Microsoft 365 Enterprise global administratör<br/>- Global administratör<br/>- Efterlevnadsadministratör<br/>– IB efterlevnadshantering (det här är en ny roll!)<br><br>Mer information om krav för informationsbarriärer finns i [Förutsättningar (för informationsbarriärprinciper).](information-barriers-policies.md#prerequisites)<br><br> Se till att [ansluta till Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

## <a name="edit-user-account-attributes"></a>Redigera användarkontoattribut

Använd den här proceduren om du vill redigera attribut som används för segmenterade användare. Om du till exempel använder ett Avdelning-attribut, och ett eller flera användarkonton för närvarande inte har några värden för Avdelning, måste du redigera dessa användarkonton så att de innehåller avdelningsinformation. Användarkontoattribut används för att definiera segment så att det går att tilldela informationsbarriärprinciper.

1. Om du vill visa information om ett visst användarkonto, till exempel attributvärden och tilldelade segment, använder du cmdlet:en **Get-InformationBarrierRecipientStatus** med identitetsparametrar.

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Du kan använda valigt värde som unikt identifierar varje användare, t.ex. namn, alias, unikt namn, kanoniskt domännamn, e-postadress eller GUID. <p> (Du kan också använda den här cmdleten för en enskild användare: `Get-InformationBarrierRecipientStatus -Identity <value>` ) |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> I det här exemplet hänvisar vi till två användarkonton i Office 365: *abbyb* för *Alex*, *och alexw* för *Alex*. |

2. Bestäm vilket attribut du vill redigera för dina användarkontoprofiler. Mer information finns i Attribut [för informationsbarriärpolicyer.](information-barriers-attributes.md) 

3. Redigera ett eller flera användarkonton och ta med värden för attributet du valde i föregående steg. Använd någon av följande metoder för att vidta den här åtgärden:

    - Om du vill redigera ett enda konto kan [du gå till Lägga till eller uppdatera en användares profilinformation med hjälp Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

    - Om du vill redigera flera konton (eller använda PowerShell för att redigera ett enda konto) går du till [Konfigurera användarkontoegenskaper med Office 365 PowerShell.](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

## <a name="edit-a-segment"></a>Redigera ett segment

Använd den här proceduren om du vill redigera definitionen för ett användarsegment. Du kan till exempel ändra namnet på ett segment eller filtret som används för att avgöra vem som ingår i segment.

1. Om du vill visa alla befintliga segment **använder du cmdleten Get-OrganizationSegment.**

    Syntax: `Get-OrganizationSegment`

    Du ser en lista över segment och information för var och en, till exempel segmenttyp, dess UserGroupFilter-värde, vem som skapade eller senast ändrade det, GUID och så vidare.

    > [!TIP]
    > Skriv ut eller spara listan med segment som referens vid ett senare tillfälle. Om du till exempel vill redigera ett segment måste du känna till dess namn eller identifiera värdet (det här används med parametern Identity).

2. Om du vill redigera ett segment använder du cmdleten **Set-OrganizationSegment** med **parametern Identity** och relevant information.

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> I det här exemplet har vi uppdaterat avdelningsnamnet till "HRDept" för det segment som har GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd.* |

När du har redigerat segmenten för din organisation kan du antingen [definiera eller](information-barriers-policies.md#part-2-define-information-barrier-policies) [redigera](#edit-a-policy) informationsbarriärprinciper.

## <a name="edit-a-policy"></a>Redigera en princip

1. Om du vill visa en lista över aktuella principer för informationsbarriärer använder du **cmdleten Get-InformationBarrierPolicy.**

    Syntax: `Get-InformationBarrierPolicy`

    Identifiera den princip du vill ändra i resultatlistan. Observera principens GUID och namn.

2. Använd **cmdleten Set-InformationBarrierPolicy** med en **Identity-parameter** och ange de ändringar du vill göra.

    Exempel: Anta att en princip har definierats för att *blockera informationssegmenten* från att kommunicera *med försäljnings-* *och marknadsföringssegmenten.* Principen har definierats med hjälp av den här cmdleten: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Anta att vi vill ändra den så att personer i *researchsegmentet* endast kan kommunicera med personer i *personalsegmentet.* För att göra den här ändringen använder vi den här cmdleten: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    I det här exemplet ändrade vi "Segment blockerade" till "SegmentsAllowed" och angav *HR-segment.*

3. När du är klar med redigeringen av en princip måste du se till att använda ändringarna. (Se [Använda principer för informationsbarriärer](information-barriers-policies.md#part-3-apply-information-barrier-policies).)

## <a name="set-a-policy-to-inactive-status"></a>Ange inaktiv status för en princip

1. Om du vill visa en lista över aktuella principer för informationsbarriärer använder du **cmdleten Get-InformationBarrierPolicy.**

    Syntax: `Get-InformationBarrierPolicy`

    Identifiera den princip som du vill ändra (eller ta bort) i resultatlistan. Observera principens GUID och namn.

2. Om du vill ange principens status som inaktiv använder du cmdleten **Set-InformationBarrierPolicy** med en Identity-parameter och stateparametern inaktiv.

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> I det här exemplet anger vi en princip för informationsbarriärer som har GUID *43c37853-ea10-4b90-a23d-ab8c9377247* till en inaktiv status. |

3. Använd cmdleten **Start-InformationBarrierPoliciesApplication om du vill** tillämpa dina ändringar.

    Syntax: `Start-InformationBarrierPoliciesApplication`

    Ändringar tillämpas, användare för användare, för organisationen. Om organisationen är stor kan det ta 24 timmar (eller mer) innan processen slutförs. (Som allmän riktlinje tar det ungefär en timme att bearbeta 5 000 användarkonton.)

I det här läget är en eller flera principer för informationsbarriärer inställda på inaktiv status. Härifrån kan du göra något av följande:

- Behåll den som den är (en princip som anges till inaktiv status påverkar inte användare)
- [Redigera en princip](#edit-a-policy) 
- [Ta bort en princip](#remove-a-policy)

## <a name="remove-a-policy"></a>Ta bort en princip

1. Om du vill visa en lista över aktuella principer för informationsbarriärer använder du **cmdleten Get-InformationBarrierPolicy.**

    Syntax: `Get-InformationBarrierPolicy`

    Identifiera den princip du vill ta bort i resultatlistan. Observera principens GUID och namn. Kontrollera att principen är inställd på inaktiv status.

2. Använd **cmdleten Remove-InformationBarrierPolicy** med en identity-parameter.

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> I det här exemplet tar vi bort principen som har GUID *43c37853-ea10-4b90-a23d-ab8c93772471.* |

    Bekräfta ändringen när du uppmanas att göra det.

3. Upprepa steg 1–2 för varje princip du vill ta bort.

4. När du är klar med att ta bort principer tillämpar du ändringarna. Använd cmdleten **Start-InformationBarrierPoliciesApplication för** att vidta den här åtgärden.

    Syntax: `Start-InformationBarrierPoliciesApplication`

    Ändringar tillämpas, användare för användare, för organisationen. Om organisationen är stor kan det ta 24 timmar (eller mer) innan processen slutförs.

## <a name="stop-a-policy-application"></a>Stoppa ett principprogram

Använd följande procedur när du har börjat tillämpa principer för informationsbarriärer, om du vill hindra att dessa principer tillämpas. Det tar ungefär 30–35 minuter innan processen kan starta.

1. Om du vill visa statusen för det senaste policyprogrammet för informationsbarriärer använder du cmdleten **Get-InformationBarrierPoliciesApplicationStatus.**

    Syntax: `Get-InformationBarrierPoliciesApplicationStatus`

    Observera programmets GUID.

2. Använd **cmdleten Stop-InformationBarrierPoliciesApplication** med en Identity-parameter.

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> I det här exemplet hindrar vi informationsbarriärer från att tillämpas. |

## <a name="resources"></a>Resurser

- [Få en översikt över informationsbarriärer](information-barriers.md)
- [Definiera principer för informationsbarriärer](information-barriers-policies.md)
- [Läs mer om informationsbarriärer i Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Läs mer om informationsbarriärer i SharePoint Online](/sharepoint/information-barriers)
- [Läs mer om informationsbarriärer i OneDrive](/onedrive/information-barriers)
- [Attribut för informationsbarriärsprinciper](information-barriers-attributes.md)
- [Felsökning av informationsbarriärer](information-barriers-troubleshooting.md)