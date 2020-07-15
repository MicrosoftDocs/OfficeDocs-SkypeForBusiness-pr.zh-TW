---
title: Microsoft 團隊中的共用線條外觀
ms.author: lolaj
author: LolaJacobsen
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft 團隊中傳送電子郵件給使用者的音訊會議資訊。
ms.openlocfilehash: 92eda8a1818d98689e71d81f31c5355df3ef1e26
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125976"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft 團隊中的共用線條外觀

共用線外觀是委派功能的一部分，可讓使用者選擇代表代表對方接聽或處理通話的代理人。 如果使用者有可定期處理使用者來電的系統管理小幫手，這項功能很有説明。 在共用線外觀的內容中，管理員是授權代理人代表自己撥打或接聽電話的人員，而代理人可以代表其他人撥打及接聽來電。

> [!IMPORTANT]
> 此功能僅適用于 [僅限團隊部署模式]。 如需有關團隊部署模式的詳細資訊，請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要授權

使用者必須有使用 PSTN 連線的電話系統（呼叫方案授權或直接路由 OnlineVoiceRoutingPolicy）作為代理人或設定委派，並允許其他人代表對方撥打或接聽電話。

管理員和代理人都需要具備 PSTN 連線的電話系統（通話方案授權或直接路由 OnlineVoiceRoutingPolicy）。 共用線體驗是委派的一部分，且包含在手機系統中。 如需授權模型的其他詳細資料，請參閱[Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>設定委派和共用線外觀

委派和共用線外觀是使用者驅動的功能：沒有要設定的系統管理員設定。 如需如何使用此功能的詳細資訊，請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租使用者管理員可以透過**TeamsCallingPolicy AllowDelegation**設定或透過團隊管理入口網站來啟用委派，這項功能才能正常運作。 

租使用者管理員也可以設定小組系統管理中心中使用者的委派關聯性。 此外，使用者也可以直接在團隊中設定其委派關聯性。 租使用者管理員或使用者無法彼此封鎖設定，但是團隊系統管理中心和團隊用戶端應該在這兩個位置中正確顯示這種關聯性。 

> [!IMPORTANT]
> 當租使用者系統管理員關閉使用者的委派功能之後（開啟之後），他們也必須在小組系統管理中心清除該使用者的委派關聯，以免呼叫路由不正確。

## <a name="shared-line-appearance-feature-availability"></a>共用線外觀功能可用性

下列應用程式和裝置目前支援共用線外觀。

| 功能 | 團隊桌面 | 團隊 Mac 應用程式 | 小組 Web App （邊緣） |團隊行動 iOS/Android 應用程式 | 團隊 IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 設定委派 | 是 | 是 | 是 | 否 | 是 |
| 代表其他方式接聽來電 | 是 | 是 | 是 | 是 | 是 |
| 代表其他電話撥打電話號碼 | 是 | 是 | 是 | 是 | 是 |
| 代表其他使用者呼叫團隊使用者 | 是 | 是 | 是 | 是 | 是 |
| 查看共用線的系統管理視圖 | 是 | 是 | 是 | 否 | 否 |
| 請參閱管理員的通話活動管理檢視 | 是 | 是 | 是 | 否 | 否 |
| 請參閱代理人的管理員視圖 | 是 | 是 | 是 | 否 | 否 |
| 系統管理員或經理可以保留或繼續 | 是 | 是 | 是 | 否 | 否 |

## <a name="limitations"></a>有限

管理員最多可以新增25個代理人，而代理人最多可有25個經理。 可在租使用者中建立的委派關聯數沒有限制。 
 
如果 delegator 和委派不在同一個地理位置，則由 PSTN 提供者允許從不同地理位置針對委派（代表的）通話顯示呼叫者 ID。 
 
## <a name="more-information"></a>詳細資訊

[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
