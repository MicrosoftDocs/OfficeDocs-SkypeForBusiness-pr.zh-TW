---
title: 在通話中呼叫Microsoft Teams
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
description: 瞭解如何在通話中使用通話保留和Microsoft Teams。
ms.openlocfilehash: 751101a250c7a3f38ac7ba51dc8a22cc91d4d7b5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772604"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>在通話中呼叫Microsoft Teams

呼叫保留和取回功能可讓使用者保留通話。 當通話被停駐時，服務會產生唯一的通話取回程序代碼。 之後，將通話停駐的使用者或其他人就可以在支援的 App 或裝置上使用該代碼來取回通話。  (請參閱[將通話Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)中，以) 

使用呼叫停駐的一些常見案例有：

- 接待員會為在工廠工作的人打電話。 然後，接待員在公用電話系統上宣佈通話和代碼號碼。 接著，通話使用者可以在工廠Teams接聽電話，然後輸入代碼以取回通話。
- 使用者將通話放在行動裝置上，因為裝置電池電力不足。 然後，使用者可以輸入代碼，從電話機Teams通話。
- 支援代表會將客戶電話放在Teams頻道上傳送公告，讓專家取回來電並協助客戶。 專家在用戶端中輸入Teams以取回通話

若要將通話停駐和取回，使用者必須是企業語音使用者，且必須包含在通話駐用策略中。

> [!NOTE]
> 呼叫停駐和Teams只能在部署模式中[](teams-and-skypeforbusiness-coexistence-and-interoperability.md)使用，IP 電話商務用 Skype不支援。

## <a name="configure-call-park-and-retrieve"></a>設定呼叫停駐和取回

您必須是管理員Teams才能設定呼叫駐位和取回。 它預設為停用。 您可以為使用者啟用它，然後使用呼叫停駐策略建立使用者群組。 當您將相同的原則套用至一組使用者時，他們可以在使用者之間停駐和取回通話。

呼叫代答號碼的範圍已預先定義為 10-99，且無法修改。 第一個已停駐的通話會呈現 10 的代答碼，下一個已停駐的通話會呈現 11 的代答碼，等等。 直到 99 呈現為代答程式碼。 之後，呈現的取件代碼會再次從 10 開始。  如果超過 89 個使用中的保留通話，則呈現的代答碼會持續遞增到 99 以上，如此一來，第 90 個有效保留的通話會呈現 100 個代答程式碼，第 91 個使用中的保留通話會呈現 101 的代答碼。

若要啟用通話停駐策略

1. 在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **通話停駐區政策**。
2. 在 [ **管理原則>** 選項卡上，按一下 [ **新增**。
3. 為策略命名，然後將允許 **通話停駐切換到****開啟**。  (無法自訂呼叫代答範圍和) 

    ![通話停駐策略設定螢幕擷取畫面](media/call-park-add-policy.png)

4. 選取 [儲存 **]**。

您可以在清單中選取該策略，然後按一下 編輯 來 **編輯。**

為了讓該策略能夠執行，必須將它指派給使用者。 您可以 [個別指派該策略](assign-policies.md) 給使用者，或將使用者指派給群組。

將呼叫停駐策略指派給群組

1. 在 [ **通話停駐點政策」** 頁面上，按一下 [ **群群組原則指派** > 的 [新增群組> 的 **[新增群組**> 。
2. 搜尋您想要使用的群組，然後按一下 [ **新增**。
3. 選擇與其他群組作業比較的排名。
4. 在 **選取策略下**，選擇要指派此群組的政策。

    ![Park policies 影像](media/call-park-assign-policy-to-group.png)

5. 選取 **Apply**。

## <a name="related-topics"></a>相關主題

[將通話Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[將原則指派給 Teams 中的使用者](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
