---
title: 在 Microsoft Teams 中撥號並擷取公園
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
description: 瞭解如何在 Microsoft Teams 中使用通話駐留和擷取來保留通話。
ms.openlocfilehash: a2a70515bbe263716fab8e2deded75e44d12fd6e
ms.sourcegitcommit: 3cb40132e36717dfbdc6dfe83e7ea319f3ec9347
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465444"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>在 Microsoft Teams 中撥號並擷取公園

通話駐留和擷取功能可讓使用者保留通話。 當通話停駐時，服務會產生唯一的呼叫擷取代碼。 停用通話的使用者或其他使用者可以使用該代碼搭配支援的應用程式或裝置來擷取通話。  (請參閱[在 Teams 中停駐通話以](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)取得詳細資料。) 

一些使用通話駐留的常見案例如下：

- 一位收件者為在工廠工作的人打電話。 然後，來電者會透過公用位址系統念出通話和代碼編號。 接聽電話的使用者可以拿起出廠樓層的Teams電話，然後輸入代碼來擷取來電。
- 使用者停用行動裝置上的通話，因為裝置電池電力不足。 使用者接著可以輸入代碼，從Teams電話機擷取來電。
- 支援代表駐留客戶電話，並在Teams頻道上傳送公告，請專家擷取來電並協助客戶。 專家在Teams用戶端中輸入代碼以擷取通話

若要駐留和擷取通話，使用者必須是企業語音使用者，而且必須包含在通話駐留原則中。

> [!NOTE]
> 通話駐留和擷取僅適用于[Teams部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md)，商務用 Skype IP 電話不支援。

## <a name="configure-call-park-and-retrieve"></a>設定通話公園並擷取

您必須是Teams系統管理員，才能設定通話公園並擷取。 預設會停用。 您可以為使用者啟用此功能，並使用通話駐留原則建立使用者群組。 當您將相同的原則套用至一組使用者時，他們可以自行駐留和擷取通話。

根據預設，接聽電話的號碼範圍是從 10 到 99。 您也可以在 10-9999 之間建立自己的自訂範圍。 第一個駐留的通話會顯示範圍 (開始的取貨代碼，例如 10) 。 下一個駐留的通話將會以 1 遞增的方式呈現取貨代碼;也就是 11，依此類型，直到範圍結束為止，才會顯示為取貨代碼。 之後，轉出的取貨代碼會從範圍開始再次開始。 

您可以將逾時指定為等候的秒數，然後在未接聽已停駐的通話時回電。 允許的範圍為 120-1800 秒，預設值為 300 秒。

若要啟用通話公園原則：

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **VoiceCall**  >  **公園原則**。
2. 在 [ **管理原則] 索引** 標籤上，按一下 [ **新增]**。
3. 為原則命名，然後將 [ **允許通話駐留]** 切換為 [ **開啟]**。
4. 視需要變更範圍和公園逾時。
5. 選取 [儲存 **]**。

您可以在清單中選取原則，然後按一下 [ **編輯] 來編輯** 原則。

若要讓原則正常運作，必須將原則指派給使用者。 您可以 [個別指派原則給使用者](assign-policies-users-and-groups.md) ，或將原則指派給群組。

將通話公園原則指派給群組

1. 在 [ **通話駐留原則** ] 頁面上，按一下 [ **群組原則指派] 索引** 標籤上的 [ **新增群組]**。
2. 搜尋您要使用的群組，然後按一下 [ **新增]**。
3. 選擇與其他群組作業比較的排名。
4. 在 **[選取原則**] 底下，選擇您要將此群組指派給的原則。

    ![公園原則圖像。](media/call-park-assign-policy-to-group.png)

5. 選取 [ **套用]**。

## <a name="related-topics"></a>相關主題

[在 Teams 中停駐通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[將原則指派給 Teams 中的使用者](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
