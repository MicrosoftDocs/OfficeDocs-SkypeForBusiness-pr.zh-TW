---
title: 呼叫停駐和Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 瞭解如何在通話中使用通話保留和Microsoft Teams。
ms.openlocfilehash: eac146ee80624152e3f0be1ab2523f848328bb95
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605799"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>呼叫停駐和Microsoft Teams

呼叫保留和取回功能可讓使用者保留通話。 當通話被停駐時，服務會產生唯一的通話取回程序代碼。 之後，將通話停駐的使用者或其他人就可以在支援的 App 或裝置上使用該代碼來取回通話。  (請參閱[將通話Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)中，以) 

使用呼叫停駐的一些常見案例有：

- 接待員會為在工廠工作的人打電話。 然後，接待員在公用電話系統上宣佈通話和代碼號碼。 接著，負責通話的使用者可以在工廠Teams接聽電話，然後輸入代碼以取回通話。
- 使用者將通話放在行動裝置上，因為裝置電池電力不足。 然後，使用者可以輸入代碼，從電話機Teams通話。
- 支援代表會將客戶電話寄到電話上，Teams頻道傳送公告，讓專家取回來電並協助客戶。 專家在用戶端中輸入Teams以取回通話

若要將通話停駐和取回，使用者必須是企業語音使用者，而且必須包含在通話駐用策略中。

> [!NOTE]
> 呼叫停駐和Teams[僅適用于部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md)，IP 電話商務用 Skype不支援。

## <a name="configure-call-park-and-retrieve"></a>設定呼叫停駐和取回

您必須是系統管理員Teams，才能設定通話停駐和取回。 它預設為停用。 您可以為使用者啟用它，然後使用呼叫停駐策略建立使用者群組。 當您將相同的原則套用至一組使用者時，他們可以在使用者之間停駐和取回通話。

根據預設，呼叫代答號碼的範圍為 10-99。 您也可以在 10-9999 之間建立自己的自訂範圍。 第一個已停駐的通話會呈現範圍起始碼的代答 (例如 10) 。 下一個已停駐的通話將會呈現遞增 1 的取件碼;也就是說，11 等等，直到範圍結尾呈現為代答程式碼。 之後，呈現的取件代碼會再次從範圍開始開始。 

您可以指定一個超時，做為等待的秒數，再在未接回已暫停的通話時回鈴。 允許的範圍為 120-1800 秒，預設值為 300 秒。

若要設定自訂的駐車範圍和停駐時間，請使用 Teams PowerShell 模組 2.6.0 或更新版本提供的 New 和 Set-CsTeamsCallParkPolicy Cmdlet。  (系統管理中心無法管理自訂Teams範圍和停駐時間變更。 請注意，Teams系統管理中心會繼續顯示預設值。) 

若要啟用通話停駐策略：

1. 在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **通話停駐策略**。
2. 在 [ **管理原則>** 選項卡上，按一下 [ **新增**。
3. 為策略命名，然後將允許 **通話停駐切換到****開啟**。  (無法自訂呼叫代答範圍和) 

    ![通話停駐策略設定螢幕擷取畫面。](media/call-park-add-policy.png)

4. 選取 [儲存 **]**。

您可以在清單中選取該策略，然後按一下 編輯 來 **編輯。**

為了讓該策略能夠執行，必須將它指派給使用者。 您可以 [個別指派該策略給使用者](assign-policies-users-and-groups.md) ，或將使用者指派給群組。

將通話停駐策略指派給群組

1. 在 [ **通話停駐點策略>** 頁面上，按一下 [ **群群組原則工作分派** > 選項卡上的 [ **新增群組**> 。
2. 搜尋您想要使用的群組，然後按一下 [ **新增**。
3. 選擇與其他群組作業比較的排名。
4. 在 **選取策略下**，選擇要指派此群組的政策。

    ![公園政策影像。](media/call-park-assign-policy-to-group.png)

5. 選取 **Apply**。

## <a name="related-topics"></a>相關主題

[將通話停在 Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[將原則指派給 Teams 中的使用者](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
