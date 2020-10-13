---
title: 在 Microsoft 團隊中通話駐留與取回
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
description: 瞭解如何使用通話駐留及取回功能，在 Microsoft 團隊中保持通話。
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424579"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>在 Microsoft 團隊中通話駐留與取回

通話駐留與取回功能可讓使用者在保留通話時撥打電話。 當通話停用時，服務會產生唯一的呼叫檢索程式碼。 停用通話的使用者，或其他人可以將該程式碼與支援的 app 或裝置搭配使用，以取得通話。  (請參閱 [在團隊中查看寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 以取得詳細資料。 ) 

使用通話駐留的一些常見案例如下：

- [接待員] 負責在工廠中使用某個人的通話。 然後，接待員會宣佈通話，並將代碼編號放在公用位址系統上。 通話的使用者可以在工廠中挑選 [團隊電話]，然後輸入程式碼來檢索通話。
- 使用者在行動裝置上公園通話，因為裝置電池已用完電源。 然後，使用者可以輸入程式碼來從小組的手機中檢索通話。
- 支援代表會公園客戶通話，並在小組頻道上傳送公告，讓專家來取得通話並協助客戶。 專家在 [團隊用戶端] 中輸入程式碼來檢索通話

若要寄存與取回通話，使用者必須是企業語音使用者，而且必須包含在通話寄存原則中。

> [!NOTE]
> 通話駐留與取回功能僅適用于 [僅限小組中的部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，且在商務用 Skype IP 手機上不受支援。

## <a name="configure-call-park-and-retrieve"></a>設定通話寄存與取回

您必須是團隊管理員，才能設定通話寄存與取回。 預設為停用。 您可以為使用者啟用它，並使用通話駐留原則來建立使用者群組。 當您將相同的原則套用到一組使用者時，他們可以在自己的情況下寄存和取回通話。

啟用通話駐留原則

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **通話寄存原則**]。
2. 在 [ **管理原則** ] 索引標籤上，按一下 [ **新增**]。
3. 為原則命名，然後將 [ **允許通話駐留** ] 切換為 [ **開啟**]。

    ![通話駐留原則設定的螢幕擷取畫面](media/call-park-add-policy.png)

4. 選取 [ **儲存**]。

您可以在清單中選取該原則，然後按一下 [ **編輯**] 來進行編輯。

若要讓原則正常運作，必須將它指派給使用者。 您可以 [將原則單獨指派給使用者](assign-policies.md) ，或指派給群組。

將呼叫部分原則指派給群組

1. 在 [ **通話駐留原則** ] 頁面的 [ **群組原則指派** ] 索引標籤上，按一下 [ **新增群組**]。
2. 搜尋您要使用的群組，然後按一下 [ **新增**]。
3. 選擇 [與其他群組指派] 相比的排名。
4. 在 [ **選取原則**] 下，選擇您要指派給此群組的原則。

    ![](media/call-park-assign-policy-to-group.png)

5. 按一下 **[** 套用]。

## <a name="related-topics"></a>相關主題

[在團隊中寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[指派策略給小組中的使用者](assign-policies.md)

[新-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[授與 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)