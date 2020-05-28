---
title: Skapa en delad postlåda
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: När en delad postlåda har skapats kan flera personer i verksamheten dela på ansvaret att läsa och svara på e-postmeddelanden som skickas till en adress.
ms.openlocfilehash: aac4966efca3dabc0edac1ceada96d2238cb266f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400106"
---
# <a name="create-a-shared-mailbox"></a>Skapa en delad postlåda 

> [!NOTE]
> Om din organisation använder en Exchange-hybridmiljö, använder du det lokala administrationscentret för Exchange när du skapar och hanterar delade postlådor. Se [Så här skapar du en delad postlåda i administrationscentret för Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)<br><br>
> Om du inte är säker på ifall du ska skapa en delad postlåda eller en Microsoft 365-grupp för Outlook, kan du läsa mer i [Jämföra grupper](../create-groups/compare-groups.md).  Observera att det för närvarande inte är möjligt att migrera en delad postlåda till en Microsoft 365-grupp. Om det är något som du vill kunna göra, kan du låta oss veta detta genom att [rösta här](https://go.microsoft.com/fwlink/?linkid=871518).

Det är enkelt att skapa en delad postlåda så att en grupp användare kan övervaka och skicka e-post från en gemensam e-postadress, exempelvis info@contoso.com. När en person i gruppen svarar på ett meddelande till den delade postlådan ser svarsmeddelandet ut att komma från den delade postlådan, inte från den enskilda användaren.

I delade postlådor finns det en delad kalender. Många små företag tycker att det är praktiskt att ha en delad kalender där alla lägger in sina avtalade tider. Om det till exempel finns tre personer som utför kundbesök kan de alla skriva in sina avtalade tider i kalendern. Det är ett bra sätt att hålla alla informerade om var alla befinner sig.

Innan du skapar en delad postlåda bör du läsa [Om delade postlådor](about-shared-mailboxes.md) för att få mer information.

## <a name="create-a-shared-mailbox-and-add-members"></a>Skapa en delad postlåda och lägg till medlemmar
  
1. Logga in med ett globalt administratörskonto eller Exchange-administratörskonto. Om du får meddelandet ”**Du har inte behörighet att komma åt den här sidan eller utföra den här åtgärden**”, är du inte någon administratör. 

::: moniker range="o365-worldwide"

2. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

2. I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041) går du till sidan **Grupper** \> **Delade postlådor**.

::: moniker-end

::: moniker range="o365-21vianet"

2. I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627) går du till sidan **Grupper** \> **Delade postlådor**.

::: moniker-end
    
3. På sidan **Delade postlådor** väljer du **+ Lägg till en postlåda**. Ange ett namn på den delade postlådan. Guiden väljer sedan e-postadress, men du kan redigera den.
    
    ![Namnge den delade postlådan.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Välj **Lägg till**. Det kan ta några minuter innan du kan lägga till medlemmar.

5. Under **Nästa steg** väljer du **Lägg till medlemmar i den här postlådan**. Medlemmarna är de personer som kan se inkommande e-post till den delade postlådan och utgående svar.

   ![Välj Lägg till medlemmar](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Välj knappen **+Lägg till medlemmar**. Markera de personer som ska använda den delade postlådan och välj **Spara**.

   ![Tilldela medlemmar till den delade postlådan](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Välj **Stäng**.

Du har en delad postlåda och den innehåller en delad kalender. Gå vidare till nästa steg: Blockera inloggning för den delade postlådans konto.

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Blockera inloggning för den delade postlådans konto

Alla delade postlådor har ett motsvarande användarkonto. Lade du märke till att du inte behövde ange något lösenord när du skapade den delade postlådan? Kontot har ett lösenord, men det genereras av systemet (okänt). Du ska inte använda kontot för att logga in på den delade postlådan.

Men vad händer om en administratör återställer lösenordet för den delade postlådans användarkonto? Eller om en angripare får åtkomst till kontoautentiseringsuppgifterna för den delade postlådan? Det skulle innebära att användarkontot kan logga in på den delade postlådan och skicka e-post. För att förhindra detta måste du blockera inloggningen för det konto som är kopplat till den delade postlådan.

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. filtret till **Användare utan licens**).

3. Välj användaren för att öppna fönstret Egenskaper och välj sedan ikonen **Blockera den här användaren** ![Skärmbild av ikonen Blockera den här användaren](../../media/block-user-icon.png).

   **Obs**! Om kontot redan är blockerat visas **Inloggning blockerad** längst upp och ikonen är **Avblockera den här användaren**.

4. I fönstret **Blockera den här användaren?** väljer du **Blockera användaren från att logga in** och sedan **Spara ändringarna**.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. vyn till **Användare utan licens**) och markera sedan kontot.

3. Välj **Blockera inloggning** i den utfällbara menyn för egenskaper.

    **Obs!** Om kontot redan har blockerats visar knappen **Tillåt inloggning**.

4. Kontrollera att Blockera användaren från att logga in är markerad i den utfällbara menyn **Redigera inloggningsstatus**. Välj **Spara** och sedan **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. vyn till **Användare utan licens**) och markera sedan kontot.

3. Välj **Blockera inloggning** i den utfällbara menyn för egenskaper.

    **Obs!** Om kontot redan har blockerats visar knappen **Tillåt inloggning**.

4. Kontrollera att Blockera användaren från att logga in är markerad i den utfällbara menyn **Redigera inloggningsstatus**. Välj **Spara** och sedan **Stäng**.
::: moniker-end

Om du vill ha anvisningar om hur du blockerar inloggning för konton som använder Azure AD PowerShell (med flera konton samtidigt), kan du läsa [Blockera användarkonton med Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).

## <a name="add-the-shared-mailbox-to-outlook"></a>Lägga till den delade postlådan i Outlook

Om ditt företag har aktiverat automatisk mappning (det har de flesta som standard), visas den delade postlådan i användarnas Outlook-app automatiskt när de har stängt och startat om Outlook. 

Automatisk mappning är inställt på användarens postlåda, inte på den delade postlådan.   Det här innebär att automatisk mappning inte fungerar om du försöker använda säkerhetsgruppen för att hantera vem som har åtkomst till den delade postlådan. Om du vill använda automatisk mappning måste du uttryckligen tilldela behörigheter. Automatisk mappning är aktiverat som standard. Mer information om hur du inaktiverar funktionen finns i [Ta bort automatisk mappning för en delad postlåda](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Mer information om delade postlådor i Outlook finns i:

- <a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Öppna och använda en delad postlåda i Outlook</a>

- <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Lägga till en delad postlåda i Outlook på webben</a>

- <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a>

- <a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Öppna en delad mapp eller postlåda i Outlook för Mac</a>

- <a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Lägga till regler i en delad postlåda</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Använda en delad postlåda på en mobil enhet (mobiltelefon eller surfplatta)

Du kan komma åt en delad postlåda på en mobil enhet på två sätt:
- Lägg till den delade postlådan i <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook för iOS-appen</a> eller <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook för Android-mobilappen</a>. 
    
    Anvisningar finns i <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a>.

- Öppna webbläsaren, logga in och gå sedan till Outlook på webben. Från Outlook på webben har du tillgång till den delade postlådan.

    Anvisningar finns i <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Lägga till en delad postlåda i Outlook på webben</a>.

## <a name="use-the-shared-calendar"></a>Använda den delade kalendern

När du skapade den delade postlådan, skapade du automatiskt en delad kalender. Vi föredrar den delade postlådekalendern framför en SharePoint-kalender när det handlar om att hålla koll på avtalade tider och var personer befinner sig. En delad kalender är integrerad med Outlook och är mycket enklare att använda än en SharePoint-kalender.

1. Öppna kalendervyn i Outlook-appen och välj den delade postlådan.

2. Alla medlemmar i den delade postlådan ser avtalade tider som du lägger in. 

3. Alla medlemmar i den delade postlådan kan skapa, visa och hantera avtalade tider i kalendern på samma sätt som med privata avtalade tider. Alla som är medlemmar i en delad postlåda kan se sina ändringar i den delade kalendern.

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)





