---
title: Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Om en användare kontinuerligt skickar e-postmeddelanden från Office 365 som klassificeras som skräppost, begränsas de från att skicka fler meddelanden.
ms.openlocfilehash: 6fad4b9d3554228bdbf474bce2b4b2d0f29f7e2b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812251"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost

Om en användare regelbundet skickar e-postmeddelanden som klassificeras som skräppost från Office 365, kommer de att begränsas från att skicka e-post, men de kan fortfarande ta emot e-post. Användaren visas i tjänsten som olämplig utgående avsändare och får en rapport om utebliven leverans (NDR) som anger:

> “Det gick inte att leverera meddelandet eftersom du inte godkändes som en giltig avsändare. Vanligtvis beror detta på att din e-postadress är misstänkt för att skicka skräppost och det är inte längre tillåten att skicka e-post.  Kontakta e-postadministratören om du behöver hjälp. Fjärrservern returnerade '550 5.1.8 åtkomst nekad, felaktig utgående avsändare”.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?
<a name="sectionSection0"> </a>

Beräknad tid: 5 minuter

Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Om du vill se vilka behörigheter du behöver kan du läsa avsnittet “Skydd mot skräppost i [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

Följande procedur kan även utföras via fjärransluten PowerShell. Använd cmdleten Get-BlockedSenderAddress för att få listan med begränsade användare och Remove-BlockedSenderAddress för att ta bort begränsningen. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Ta bort begränsningar för ett blockerat Office 365-e-postkonto

Du slutför den här uppgiften i Säkerhets- och efterlevnadscentret (SCC). [Gå till Säkerhets- och efterlevnadscentret](../../compliance/go-to-the-securitycompliance-center.md) om du vill ha mer information om SCC. Du måste vara med i rollgrupperna**Organisationshantering** eller **Säkerhetsadministratör** för att kunna utföra de här funktionerna. [Gå till Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md) om du vill ha mer information om SCC-rollgrupper.

1. Använd ett arbets- eller skolkonto som har globala åtkomstbehörigheter för administratörer i Office 365, logga in i Säkerhets- och efterlevnadscentret i Office 365 och visa **Hothantering** i listan till vänster, välj **Granska**och välj sedan **Begränsade användare**.

    > [!TIP]
    > Om du vill gå direkt till sidan **Begränsad användare** (tidigare kallat Aktivitetscentret) i Säkerhets-&amp; och efterlevnadscentret använder du följande URL: [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Den här sidan innehåller en lista med användare som har blockerats från att skicka e-post.  Leta rätt på den användare som du vill ta bort restriktioner från och välj **Avblockera**.

3. En utfällbar meny kommer att visa information om det konto vars sändning är begränsad. Vi rekommenderar att du går igenom rekommendationerna för att se till att du vidtar lämpliga åtgärder om kontot faktiskt är komprometterat. Välj **Nästa** när du är klar.

4. På nästa skärm finns rekommendationer för att förhindra framtida intrång. Att aktivera multifaktorautentisering (MFA) och ändra lösenord är ett bra skydd. Klicka **Avblockera användare** när du är klar.

5. Bekräfta ändringen genom att klicka på **Ja**.

    > [!NOTE]
    > Det kan ta 30 minuter eller mer innan restriktioner tas bort.

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Att se till att administratörer varnas när detta händer

Varningen "Användare begränsas från att skicka e-post" är tillgänglig som policy på sidan med säkerhets- och aviseringsprinciper för Office 365. Detta var tidigare den utgående skräppostprincipen, men är nu inbyggd i varningsplattformen i Office 365. Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningar.

> [!IMPORTANT]
> För att varningar ska fungera måste Granskningsloggsökning aktiveras. Du kan läsa hur man gör i [Aktivera och inaktivera granskningsloggsökning för Office 365](../../compliance/turn-audit-log-search-on-or-off.md).

Principen för den här varningen är en standardprincip och medföljer alla Office 365-klientorganisationer och behöver inte konfigureras. Det anses vara ett varningsmeddelande med hög allvarlighetsgrad och kommer att skickas till den konfigurerade TenantAdmins-gruppen när meddelandet skickas då en användare har begränsats från att skicka e-post. Administratörer kan uppdatera den grupp som meddelas när denna varning görs genom att gå till varningen under SCC-portalen > Varningar > Varningsregler > Användare som begränsats från att skicka e-post.

Du kan redigera varningen på följande sätt:
- Aktivera/inaktivera e-postaviseringar
- Skicka e-post till nödvändiga mottagare
- Begränsa antalet dagliga aviseringar du tar emot

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>Söka efter och ta bort restriktioner med PowerShell
PowerShell-kommandon för begränsade användare är:
- `Get-BlockedSenderAddress`: Kör för att hämta listan över användare som begränsas från att skicka e-post
- `Remove-BlockedSenderAddress`: Kör för att ta bort användare från att begränsas

## <a name="for-more-information"></a>Mer information

[Svara på ett komprometterat e-postkonto](responding-to-a-compromised-email-account.md)

[Information om användaren som begränsas från att skicka e-postavisering](https://docs.microsoft.com/office365/securitycompliance/alert-policies)

[Pool med hög riskleverans för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md)

[Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md)

[Aviseringsregler i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/office365/securitycompliance/alert-policies)
