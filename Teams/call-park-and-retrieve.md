---
title: 在 Microsoft Teams 中呼叫停駐和取回
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中使用通話保留和取回來保留通話。
ms.openlocfilehash: 11c0abc5c9cd49a524417ce9706129cea9ccae1e
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197578"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>在 Microsoft Teams 中呼叫停駐和取回

呼叫保留和取回功能可讓使用者保留通話。 當通話被停駐時，服務會產生唯一的通話取回程序代碼。 之後，將通話停駐的使用者或其他人就可以在支援的 App 或裝置上使用該代碼來取回通話。  (請參閱將通話停在 [Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 中以) 

使用呼叫停駐的一些常見案例有：

- 接待員會為在工廠工作的人打電話。 然後，接待員在公用電話系統上宣佈通話和代碼號碼。 接著，通話使用者就可以在工廠區拿起 Teams 電話，然後輸入代碼以取回通話。
- 使用者將通話放在行動裝置上，因為裝置電池電力不足。 然後，使用者可以輸入代碼，以從 Teams 電話機取回通話。
- 支援代表會將客戶電話寄到客戶電話上，並傳送公告給 Teams 頻道，讓專家取回通話並協助客戶。 專家在 Teams 用戶端中輸入代碼以取回通話

使用者必須是企業語音使用者，且必須包含在通話停駐策略中，以將通話停駐和接聽來電。

> [!NOTE]
> 只有 Teams 部署模式才提供通話駐點和取回 [功能](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，商務用 Skype IP 電話不支援。

## <a name="configure-call-park-and-retrieve"></a>設定呼叫停駐和取回

您必須是 Teams 系統管理員，才能設定通話停駐和取回。 它預設為停用。 您可以為使用者啟用它，然後使用呼叫停駐策略建立使用者群組。 當您將相同的原則套用至一組使用者時，他們可以在使用者之間停駐和取回通話。

若要啟用通話停駐策略

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **Voice**  >  **Call Park 策略**。
2. 在 [ **管理原則>** 選項卡上，按一下 [ **新增**。
3. 為策略命名，然後將允許 **通話停駐切換到****開啟**。

    ![通話停駐策略設定螢幕擷取畫面](media/call-park-add-policy.png)

4. 選取 **儲存**。

您可以在清單中選取該策略，然後按一下編輯來 **編輯。**

為了讓該策略能夠執行，必須將它指派給使用者。 您可以 [個別指派該策略](assign-policies.md) 給使用者，或將使用者指派給群組。

將呼叫停駐策略指派給群組

1. 在 [ **通話停駐點政策」** 頁面上，按一下 [ **群群組原則指派** > 的 [新增群組> 的 **[新增群組**> 。
2. 搜尋您想要使用的群組，然後按一下 [ **新增**。
3. 選擇與其他群組作業比較的排名。
4. 在 **選取策略下**，選擇要指派此群組的政策。

    ![Park policies 影像](media/call-park-assign-policy-to-group.png)

5. 選取 **Apply**。

## <a name="related-topics"></a>相關主題

[將通話停在 Teams 中](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[將原則指派給 Teams 中的使用者](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)