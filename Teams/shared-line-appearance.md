---
title: Microsoft Teams 中的共用線條外觀
author: CarolynRowe
ms.author: crowe
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
description: 瞭解如何在 Microsoft Teams 中傳送含有音訊會議資訊的電子郵件給使用者。
ms.openlocfilehash: 3646cf27e22f5224dc825c758f757cc04d5804fc
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794321"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共用線條外觀

共用行外觀是委派功能的一部分，可讓使用者選擇代理人代表其接聽或處理通話。 如果使用者有定期處理使用者通話的系統管理助理，這項功能就很有説明。 在共用行外觀的情境中，主管是指授權代理人代表其撥打或接聽電話的人，而代理人可以代表他人撥打和接聽電話。

> [!IMPORTANT]
> 此功能僅適用于 Teams 部署模式。 如需 Teams 部署模式的詳細資料，請參閱[瞭解 Microsoft Teams 和商務用 Skype共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要授權

使用者必須具備具有 PSTN 連線能力的電話系統 (通話方案授權或直接路由 OnlineVoiceRoutingPolicy) 成為代理人，或設定委派，並讓其他人代表他們撥打或接聽電話。

主管和代理人都必須有具有 PSTN 連線的電話系統 (通話方案授權或直接路由 OnlineVoiceRoutingPolicy) 。 共用行體驗是委派的一部分，並包含在 [電話系統] 中。 如需授權模型的其他詳細資料，請參閱 [Microsoft Teams 服務說明](/office365/servicedescriptions/teams-service-description)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>設定委派和共用行外觀

委派和共用線條外觀是使用者導向的功能：沒有要設定的系統管理員設定。 如需如何使用此功能的相關資訊，請參閱 [與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租使用者管理員可以透過 **TeamsCallingPolicy AllowDelegation** 設定或透過 Teams 管理員 入口網站啟用委派，讓此功能正常運作。 

租使用者系統管理員也可以在 Teams 系統管理中心為使用者設定委派關係。 此外，使用者也可以直接在 Teams 中設定其委派關係。 租使用者系統管理員或使用者無法互相封鎖設定，但 Teams 系統管理中心和 Teams 用戶端應在這兩個地方正確顯示此關聯。 

> [!IMPORTANT]
> 當租使用者系統管理員在使用者 (開啟) 之後關閉委派時，他們也需要在 Teams 系統管理中心為該使用者清理委派關係，以避免錯誤的通話路由。

## <a name="shared-line-appearance-feature-availability"></a>共用線條外觀功能可用性

下列應用程式和裝置目前支援共用線條外觀。

| 功能 | Teams 電腦版 | Teams Mac App | Teams Web App (Edge)  |Teams 行動裝置版 iOS/Android App | Teams IP 手機 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 設定委派 | 是 | 是 | 是 | 否 | 是 |
| 代表另一個接聽來電 | 是 | 是 | 是 | 是 | 是 |
| 代表另一個電話號碼撥打 | 是 | 是 | 是 | 是 | 是 |
| 代表另一位 Teams 使用者撥打電話 | 是 | 是 | 是 | 是 | 是 |
| 查看共用行的代理人檢視 | 是 | 是 | 是 | 否 | 是 |
| 查看主管通話活動的代理人檢視 | 是 | 是 | 是 | 否 | 是 |
| 查看代理人的管理員檢視 | 是 | 是 | 是 | 否 | 是 |
| 代理人或主管可以按住或繼續 | 是 | 是 | 是 | 否 | 是 |

## <a name="limitations"></a>限制

主管最多可以新增 25 位代理人，而代理人最多可以有 25 位主管。 您可以在租使用者中建立的委派關聯數目沒有限制。 
 
如果委派者和代理人不在同一個地理位置，PSTN 提供者必須允許來電者代表) 來電，從不同的地理位置顯示委派的 (。 

不允許迴圈委派設定。 如果委派的使用者之間也有代理人，他們就只能查看其委派，而無法看到初始委派。
 
## <a name="more-information"></a>詳細資訊

[與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
