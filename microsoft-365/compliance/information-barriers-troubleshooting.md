---
title: Felsökning av informationsbarriärer
description: Använd den här artikeln som en guide för att felsöka informationsbarriärer.
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162323"
---
# <a name="troubleshooting-information-barriers"></a>Felsökning av informationsbarriärer

[Informationsbarriärer](information-barriers.md) kan hjälpa din organisation att uppfylla juridiska krav och branschföreskrifter. Om du till exempel har informationsbarriärer kan du begränsa kommunikationen mellan specifika grupper av användare för att undvika en intressekonflikt eller andra problem. (Mer information om hur du ställer in informationsbarriärer finns i [Definiera principer för informationsbarriärer](information-barriers-policies.md).)

Om personer skulle få problem när informationsbarriärer finns kan du vidta några åtgärder för att lösa problemen. Använd den här artikeln som en guide.

> [!IMPORTANT]
> För att utföra de uppgifter som beskrivs i den här artikeln måste du ha tilldelats en lämplig roll, till exempel något av följande:<br/>- Microsoft 365 Enterprise global administratör<br/>- global administratör<br/>- Efterlevnadsadministratör<br/>– IB efterlevnadshantering (det här är en ny roll!)<p>Mer information om krav för informationsbarriärer finns i [Förutsättningar (för informationsbarriärprinciper).](information-barriers-policies.md#prerequisites)<p>Se till att [ansluta till Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problem: Användare blockeras oväntat från att kommunicera med andra i Microsoft Teams 

I det här fallet rapporterar personer oväntade problem när de kommunicerar med andra i Microsoft Teams. Några exempel är:

- En användare söker efter, men kan inte hitta, en annan användare i Microsoft Teams.
- En användare kan hitta, men inte välja, en annan användare i Microsoft Teams.
- En användare kan se en annan användare, men kan inte skicka meddelanden till den andra användaren Microsoft Teams.

### <a name="what-to-do"></a>Vad kan jag göra?

Bestäm om användarna påverkas av en informationsbarriärpolicy. Beroende på hur principer konfigureras kanske informationsbarriärer fungerar som förväntat. Eller så kanske du måste förfina organisationens principer.

1. Använd **cmdleten Get-InformationBarrierRecipientStatus** med identityparametern. 

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> Du kan använda alla identitetsvärden som unikt identifierar varje mottagare, som Namn, Alias, Unikt namn (DN), Canonical DN, E-postadress eller GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> I det här exemplet använder vi ett alias *(mer information)* för parametern Identity. Denna cmdlet returnerar information som anger om användaren påverkas av en informationsbarriärpolicy. (Titta efter *ExoPolicyId: \<GUID> .) |

    **Om användarna inte omfattas av informationsbarriärpolicyn kontaktar du supporten.** Annars går du vidare till nästa steg.

2. Ta reda på vilka segment som ingår i en informationsbarriärpolicy. Det gör du genom att `Get-InformationBarrierPolicy` använda cmdleten med parametern Identity. 

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Använd information, till exempel den princip-GUID (ExoPolicyId) som du fick i föregående steg, som ett identitetsvärde. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> I det här exemplet får vi detaljerad information om informationsbarriärpolicyn som har ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*. |

    När du har kört cmdleten letar du efter värden **för Tilldelade segment,** **SegmentAlla** och **Blockerade segment i** resultatet.

    När vi till exempel körde `Get-InformationBarrierPolicy` cmdleten såg vi följande i vår resultatlista:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    I det här fallet kan vi se att en princip om informationsbarriärer påverkar personer som finns i segmenten Försäljning och forskning. I det här fallet hindras säljarna från att kommunicera med personer inom forskning.

    Om detta verkar vara rätt fungerar informationsbarriärer som förväntat. Annars går du vidare till nästa steg.

3. Kontrollera att dina segment är rätt definierade. Det gör du genom att `Get-OrganizationSegment` använda cmdleten och granska resultatlistan.

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Använd den här cmdleten med en Identity-parameter. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> I det här exemplet får vi information om det segment som har GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Granska informationen för segment. Om det behövs [redigerar du ett segment](information-barriers-edit-segments-policies.md#edit-a-segment)och använder sedan `Start-InformationBarrierPoliciesApplication` cmdleten.

    Kontakta support om du fortfarande har problem med **informationsbarriärpolicyn.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problem: Kommunikation är tillåten mellan användare som ska blockeras i Microsoft Teams

I det här fallet även om informationsbarriärer definieras, är aktiva och tillämpas kan personer som borde hindras från att kommunicera med varandra i från att chatta med varandra och ringa varandra i Microsoft Teams.

### <a name="what-to-do"></a>Vad kan jag göra?

Kontrollera att användarna i fråga finns med i informationsbarriärpolicyn. 

1. Använd **cmdleten Get-InformationBarrierRecipientStatus** med identitetsparametrar.

    |**Syntax** _|_ *Exempel**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Du kan använda valigt värde som unikt identifierar varje användare, t.ex. namn, alias, unikt namn, kanoniskt domännamn, e-postadress eller GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> I det här exemplet hänvisar vi till två användarkonton i Office 365: *abbyb* för *Alex*, *och alexw* för *Alex*. |

    > [!TIP]
    > Du kan också använda den här cmdleten för en enskild användare: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Granska resultaten. Cmdleten **Get-InformationBarrierRecipientStatus** returnerar information om användare, till exempel attributvärden och eventuell informationsbarriärpolicy som tillämpas.

    Granska resultatet och vidta sedan nästa steg, enligt beskrivningen i följande tabell:

    |**Resultat**|**Vad ska jag göra härnäst?**|
    |:----------|:------------------|
    | Inga segment visas för de valda användarna | Gör något av följande:<br/>– Tilldela användare till ett befintligt segment genom att redigera användarprofilerna i Azure Active Directory. (Se [Konfigurera användarkontoegenskaper med Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).)<br/>- Definiera ett segment med ett [attribut som stöds för informationsbarriärer.](information-barriers-attributes.md) Definiera sedan en [ny princip eller redigera](information-barriers-policies.md#part-2-define-information-barrier-policies) en befintlig princip [så](information-barriers-edit-segments-policies.md#edit-a-policy) att den omfattar det segment. |
    | Segment listas men inga informationsbarriärer kopplas till de segmenten | Gör något av följande:<br/>- [Definiera en ny princip för informationsbarriärer](information-barriers-policies.md#part-2-define-information-barrier-policies) för varje segment i fråga <br/>- [Redigera en befintlig princip för informationsbarriärer](information-barriers-edit-segments-policies.md#edit-a-policy) för att tilldela den till rätt segment |
    | Segment listas och var och en omfattas av en informationsbarriärpolicy | - Kör `Get-InformationBarrierPolicy` cmdleten för att verifiera att informationsbarriärprinciper är aktiva<br/>- Kör `Get-InformationBarrierPoliciesApplicationStatus` cmdleten för att bekräfta att principerna används<br/>- Kör `Start-InformationBarrierPoliciesApplication` cmdleten för att tillämpa alla aktiva informationsbarriärprinciper |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problem: Jag behöver ta bort en enskild användare från en informationsbarriärpolicy

I det här fallet finns det principer för informationsbarriärer och en eller flera användare blockeras oväntat från att kommunicera med andra i Microsoft Teams. I stället för att ta bort principer för informationsbarriärer helt och hållet kan du ta bort en eller flera enskilda användare från informationsbarriärprinciper.

### <a name="what-to-do"></a>Vad kan jag göra?

Informationsbarriärprinciper kopplas till segment av användare. Segment definieras med hjälp av [vissa attribut i användarprofilen.](information-barriers-attributes.md) Om du måste ta bort en princip från en enskild användare kan du redigera den användarens profil i Azure Active Directory så att den inte längre ingår i ett segment som påverkas av informationsbarriärer.

1. Använd **cmdleten Get-InformationBarrierRecipientStatus** med identitetsparametrar. Den här cmdleten returnerar information om användare, till exempel attributvärden och informationsbarriärprinciper som tillämpas.

    |**Syntax**|**Exempel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Du kan använda valigt värde som unikt identifierar varje användare, t.ex. namn, alias, unikt namn, kanoniskt domännamn, e-postadress eller GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> I det här exemplet hänvisar vi till två användarkonton i Office 365: *abbyb* för *Alex*, *och alexw* för *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> Du kan använda alla värden som unikt identifierar användaren, till exempel namn, alias, unikt namn, kanoniskt domännamn, e-postadress eller GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> I det här exemplet refererar vi till ett enda konto i Office 365: *Office 365 .* |

2. Granska resultaten för att se om principer för informationsbarriärer har tilldelats och till vilka segment användaren/användarna tillhör.

3. Om du vill ta bort en användare från ett segment som påverkas av informationsbarriärer uppdaterar du [användarens profilinformation i Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

4. Vänta cirka 30 minuter på att FwdSync visas. Eller kör `Start-InformationBarrierPoliciesApplication` cmdleten för att tillämpa alla aktiva informationsbarriärprinciper.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problem: Programprocessen för informationsbarriärer tar för lång tid

När du **har kört cmdleten Start-InformationBarrierPoliciesApplication** tar det mycket lång tid att slutföra processen.

### <a name="what-to-do"></a>Vad kan jag göra?

Kom ihåg att när du kör cmdleten för policyprogrammet tillämpas (eller tas bort) informationsbarriärprinciper per användare för alla konton i organisationen. Om du har många användare tar det en stund att bearbeta. (Som allmän riktlinje tar det ungefär en timme att bearbeta 5 000 användarkonton.)

1. Använd **cmdleten Get-InformationBarrierPoliciesApplicationStatus** för att verifiera statusen för det senaste principprogrammet.

    |**Så här visar du det senaste principprogrammet**|**Visa status för alla principprogram**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Här visas information om huruvida programmet har slutförts, misslyckats eller pågår.

2. Beroende på resultatet av föregående steg gör du något av följande:
  
    |**Status**|**Nästa steg**|
    |:---------|:------------|
    | **Ej startad** | Om det har gått mer än 45 minuter sedan cmdleten **Start-InformationBarrierPoliciesApplication** har körts kan du granska granskningsloggen för att se om det finns fel i principdefinitioner eller någon annan orsak till att programmet inte har startat. |
    | **Misslyckades** | Om programmet misslyckades granskar du granskningsloggen. Granska även segment och principer. Är några användare tilldelade till mer än ett segment? Är några segment tilldelade mer än en politisk? Om det behövs [kan du redigera](information-barriers-edit-segments-policies.md#edit-a-segment) segment och/eller redigera principer och sedan köra **cmdleten Start-InformationBarrierPoliciesApplication** igen. [](information-barriers-edit-segments-policies.md#edit-a-policy) |
    | **Pågående** | Om programmet fortfarande pågår kan du ge det mer tid att slutföra. Om det har gått flera dagar samlar du in granskningsloggarna och kontaktar sedan supporten. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problem: Principer för informationsbarriärer tillämpas inte alls

I det här fallet har du definierat segment, definierat principer för informationsbarriärer och har försökt tillämpa dessa principer. Men när du kör `Get-InformationBarrierPoliciesApplicationStatus` cmdleten kan du se att principprogrammet har misslyckats.

### <a name="what-to-do"></a>Vad kan jag göra?

Kontrollera att organisationen inte har några [Exchange finns adressboksprinciper.](/exchange/address-books/address-book-policies/address-book-policies) Sådana principer förhindrar att informationsbarriärer tillämpas.

1. Anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör [cmdleten Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) och granska resultaten.

    |**Resultat**|**Nästa steg**|
    |:----------|:------------|
    | Exchange adressboksprinciper visas | [Ta bort adressboksprinciper](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | Det finns inga adressboksprinciper |Granska granskningsloggarna för att ta reda på varför principprogrammet inte fungerar |

3. [Visa status för användarkonton, segment, principer eller principprogram.](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problem: Policy för informationsbarriärer tillämpas inte för alla angivna användare

När du har definierat segment, definierat principer för informationsbarriärer och försökt tillämpa dessa principer, kan det hända att principen gäller för vissa mottagare, men inte för andra.
När du kör `Get-InformationBarrierPoliciesApplicationStatus` cmdleten söker du i resultatet efter text som den här.

> Identitet: `<application guid>`
>
> Totalt antal mottagare: 81527
>
> Misslyckade mottagare: 2
>
> Felkategori: Ingen
>
> Status: Slutförd

### <a name="what-to-do"></a>Vad kan jag göra?

1. Sök i granskningsloggen efter `<application guid>` . Du kan kopiera den här PowerShell-koden och ändra för dina variabler.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Kontrollera detaljerad information från granskningsloggen efter värdena för `"UserId"` fälten `"ErrorDetails"` och. På så sätt får du orsaken till felet. Du kan kopiera den här PowerShell-koden och ändra för dina variabler.

```powershell
   $DetailedLogs[1] |fl
```

Till exempel:

> "UserId": Användare1
>
>"ErrorDetails":"Status: IBPolicyConflict. Fel: Segmentet IB "segment-id1" och IB-segment "segment-id2" är i konflikt och kan inte tilldelas till mottagaren.

3. Vanligtvis upptäcker du att en användare har inkluderats i mer än ett segment. Du kan åtgärda detta genom att uppdatera `-UserGroupFilter` värdet i `OrganizationSegments` .

4. Tillämpa informationsbarriärprinciper på annat sätt med hjälp av dessa [procedurer Informationsbarriärpolicyer.](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="resources"></a>Resurser

- [Definiera principer för informationsbarriärer i Microsoft Teams](information-barriers-policies.md)
- [Informationsbarriärer](information-barriers.md)