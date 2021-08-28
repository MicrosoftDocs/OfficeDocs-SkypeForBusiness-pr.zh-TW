---
title: 共用線條外觀Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
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
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中傳送包含其音訊會議資訊Microsoft Teams。
ms.openlocfilehash: e9954f85d9f5676635dc8d4616c08d0e0d3ac6be
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617169"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>共用線條外觀Microsoft Teams

共用線路外觀是委派功能之一，讓使用者選擇代理人來代表他們接聽或處理通話。 如果使用者有系統管理助理定期處理使用者的通話，這項功能會很有説明。 在共用線路外觀中，主管是授權代理人代表代理人撥打或接聽電話的人，代理人可以代表其他人撥打和接聽電話。

> [!IMPORTANT]
> 此功能僅適用于僅部署Teams模式。 有關部署模式Teams詳細資料，請參閱瞭解[Microsoft Teams商務用 Skype和](teams-and-skypeforbusiness-coexistence-and-interoperability.md)互通性

## <a name="license-required"></a>需要授權

使用者必須擁有電話系統 PSTN 連線 (電話方案授權或直接路由 OnlineVoiceRoutingPolicy) 才能成為代理人或設定委派，並讓他人代表他們撥打或接聽電話。

管理員和代理人必須電話系統 PSTN 連線 (通話方案授權或直接路由 OnlineVoiceRoutingPolicy) 。 共用線路體驗是委派的一部分，並包含在電話系統。 有關授權模型的其他詳細資料，請參閱Microsoft Teams[描述](/office365/servicedescriptions/teams-service-description)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>配置委派和共用行外觀

委派和共用行外觀是使用者導向的功能：不需要設定系統管理員設定。 若要瞭解如何使用此功能，請參閱與代理人共用 [電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租使用者系統管理員可以透過 **TeamsCallingPolicy AllowDelegation** 設定或透過 Teams 系統管理入口網站啟用委派，讓此功能能夠執行。 

租使用者系統管理員也可以為系統管理中心中的使用者Teams關係。 此外，使用者也可以直接在 Teams 中設定其委派Teams。 租使用者系統管理員或使用者無法彼此封鎖該組Teams，但系統管理中心Teams用戶端應該在這兩個地方正確顯示此關係。 

> [!IMPORTANT]
> 當租使用者系統管理員在) 開啟使用者 (後關閉使用者的委派時，他們也需要在 Teams 系統管理中心清理該使用者的委派關係，以避免不正確的通話路由。

## <a name="shared-line-appearance-feature-availability"></a>共用線條外觀功能可用性

下列應用程式與裝置目前支援共用線路外觀。

| 功能 | Teams桌面 | TeamsMac App | TeamsWeb App (Edge)  |Teams行動版 iOS/Android App | TeamsIP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 設定委派 | 是 | 是 | 是 | 否 | 是 |
| 代表另一人接聽來電 | 是 | 是 | 是 | 是 | 是 |
| 代表另一個人撥打電話號碼 | 是 | 是 | 是 | 是 | 是 |
| 代表Teams打電話給使用者 | 是 | 是 | 是 | 是 | 是 |
| 查看共用行的系統管理員視圖 | 是 | 是 | 是 | 否 | 否 |
| 查看管理員通話活動的系統管理員視圖 | 是 | 是 | 是 | 否 | 否 |
| 查看代理人的管理員視圖 | 是 | 是 | 是 | 否 | 否 |
| 系統管理員或主管可以保留或繼續 | 是 | 是 | 是 | 否 | 否 |

## <a name="limitations"></a>限制

主管最多可以新增 25 個代理人，而代理人最多可以有 25 個主管。 在租使用者中可以建立委派關係的數量沒有限制。 
 
如果委派者與代理人不在同一個地理位置，則由 PSTN 提供者代表) 通話，允許代理人的本機號碼不同的地理位置 (本機號碼。 
 
## <a name="more-information"></a>詳細資訊

[與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)