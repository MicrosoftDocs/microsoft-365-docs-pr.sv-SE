---
title: Steg 7 – Ta bort en tidigare anställds användarkonto
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Följ de här stegen om du vill ta bort en tidigare anställds användarkonto.
ms.openlocfilehash: 5ca428079091c4af44ef1efa9be3d7340e254995
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535944"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Steg 7 – Ta bort en tidigare anställds användarkonto

När du har sparat och kommit åt den tidigare anställdes alla användardata kan du ta bort den tidigare anställdes konto.

> [!IMPORTANT]
> Ta inte bort kontot om du har konfigurerat vidarebefordran av e-post eller konverterat postlådan till en delad postlåda. Kontot krävs för att kunna använda vidarebefordran av e-post eller den delade postlådan.

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera namnet på den anställda som du vill ta bort.
3. Under användarens namn väljer du Ta **bort användare.** Välj de alternativ du vill använda för användaren och välj sedan Ta **bort användare.** Om du redan har gett en annan användare åtkomst till den här användarens e-OneDrive behöver du inte göra det igen här.

När du tar bort en användare blir dennes konto inaktivt i ca 30 dagar. Du har tills dess på dig att återställa kontot innan det tas bort permanent.

## <a name="watch-delete-a-former-employees-user-account"></a>Titta: Ta bort en tidigare anställds användarkonto

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).

## <a name="does-your-organization-use-active-directory"></a>Använder ni Active Directory i organisationen?

Om din organisation synkroniserar användarkonton till Microsoft 365 från en lokal Active Directory-miljö måste du ta bort och återställa dessa användarkonton i den lokala Active Directory-tjänsten. Du kan inte ta bort eller återställa dem i Office 365.

Mer information om hur du tar bort och återställer användarkonton i Active Directory finns [i Ta bort ett användarkonto.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))
  
Om du använder en Azure Active Directory, se [PowerShell-cmdleten Remove-MsolUser.](https://go.microsoft.com/fwlink/?linkid=842230)
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Vad du behöver veta om att avsluta en anställds e-postsession

Här finns information om hur du avslutar en anställds e-post (Exchange).
  
|||
|:-----|:-----|
|**Vad du kan göra** <br/> |**Hur gör du det?** <br/> |
|Avsluta en session (till exempel Outlook på webben, Outlook, Exchange ActiveSync, etc.) och framtvinga en ny session  <br/> |Återställa lösenord  <br/> |
|Avsluta en session och blockera åtkomst till framtida sessioner (för alla protokoll)  <br/> |Inaktivera kontot. Till exempel (i Exchange eller med PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Avbryt sessionen för ett visst protokoll (till exempel ActiveSync)  <br/> |Inaktivera protokollet. Till exempel (i Exchange eller med PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

Åtgärderna ovan kan utföras på tre platser:
  
|||
|:-----|:-----|
|**Om du avslutar sessionen här** <br/> |**Hur lång tid det tar** <br/> |
|I administrationscentret för Exchange eller med PowerShell  <br/> |Förväntad fördröjning mindre än 30 minuter  <br/> |
|I Azure Active Directory-administratörcenter  <br/> |Förväntad fördröjning mindre än 60 minuter  <br/> |
|I en lokal miljö  <br/> |Förväntad fördröjning 3 timmar eller mer  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Så här får du snabbast svar vid kontouppsägning

 **Snabbast**: Använd administrationscentret för Exchange (använd PowerShell) eller administrationscentret för Azure Active Directory. Det kan ta flera timmar att synkronisera ändringar genom DirSync i en lokal miljö.
  
 **Snabbast för en användare med närvaro lokalt och i Exchange-datacentret**: Avbryt sessionen med administrationscentret för Azure Active Directory/administrationscentret för Exchange OCH gör även ändringen i den lokala miljön. Ändringen i administrationscentret för Azure Active Directory/administrationscentret för Exchange kommer annars att skrivas över av DirSync.
  
## <a name="related-articles"></a>Relaterade artiklar

[Återställa en användare](restore-user.md)

[Återställa lösenord](reset-passwords.md)
