---
title: 音訊會議撥出/以分鐘撥號給我
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-mar2020
description: 撥出及撥打電話給我的分鐘數權益。 自 2019 年 12 月 1 日起，每個音訊會議訂閱每一使用者每個月可提供 60 分鐘到區域 A 國家/地區。
ms.openlocfilehash: ee309bc579ae1360763ff0d77fad7eb3c22b3c5a
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918929"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音訊會議訂閱「撥出」/「請用電話給我」通話分鐘數權益

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Microsoft Teams 和商務用 Skype PSTN 音訊會議

每個音訊會議訂閱每個月提供每個使用者 60 分鐘，可用來撥打到任一區域 A 國家/地區中的非付費號碼，如本檔所述。 您的租使用者撥出分鐘數資料庫大小是根據購買 *授權* 。 這項權益適用于音訊會議 *每月訂閱* 授權，但不適用於音訊會議按分鐘付費授權。 

> [!NOTE]
> 自 2020 年 10 月 22 日起，租使用者撥出分鐘數資料庫的大小是根據購買的音訊會議訂閱授權數目。 之前，撥出分鐘數資料庫大小是根據指派給使用者授權的數量。 


> [!NOTE]
> 音訊會議訂閱可用[](complimentary-dial-out-period.md)的國家/地區並未在 2019 年 11 月 30 日結束撥號期間，但我們目前不提供設定通訊信用額度的能力。 這些特定國家/地區包括俄羅斯、南韓和臺灣。

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音訊會議「從會議撥出」&「撥號給我」詳細資料

針對採用音訊會議服務的客戶，Microsoft 提供由指派有音訊會議訂閱授權之使用者組織的會議撥出功能。 撥出到不在 [區域 A](audio-conferencing-zones.md) 國家/地區清單中的國家/地區撥出電話，是使用 Communications Credit 每分鐘計費。 對於超過租使用者撥出分鐘數計算區數的撥出電話 (通話，或撥打到不在 [區域 A](audio-conferencing-zones.md) 國家/地區清單中的目的地的撥出電話，通話及其相關聯的費率是根據通話的目的地，而非會議管理員的居住國家/地區或啟動撥出電話的會議參與者。 例如，如果音訊會議撥出電話是由美國、法國或法國的會議參與者所啟動，則撥打至法國地區 A 國家/地區的電話號碼，其費率會以相同的每分鐘費率計費。 


|會議召集人授權使用位置 |已撥號目的地 |我可以使用撥出分鐘數的分鐘數嗎？|我是否需要通訊信用額度？|
|---------|---------|---------|---------|
|美國 |美國 |是 (國家/地區)  |在 *耗用* 租使用者分鐘數資料庫之後是         |
|美國 |英國|是 (國家/地區)  |  在 *耗用* 租使用者分鐘數資料庫之後是       |
|美國     |辛巴威|    否     |     所有通話 *都* 支援    |
|英國     |英國|是 (國家/地區)  |  在 *耗用* 租使用者分鐘數資料庫之後是       |
|英國     |美國 |是 (國家/地區)  |  在 *耗用* 租使用者分鐘數資料庫之後是       |
|英國     |辛巴威|    否     |   所有通話 *都* 支援      |
|辛巴威     |辛巴威|    否     |    所有通話 *都* 支援     |
|辛巴威     |美國 | 是 (國家/地區)  | 在 *耗用* 租使用者分鐘數資料庫之後是        |
|辛巴威     |英國 | 是 (國家/地區)  | 在 *耗用* 租使用者分鐘數資料庫之後是        |
|科克群島     |科克群島 |   否      |    所有通話 *都* 支援     |
|科克群島     |美國  | 是 (國家/地區)  |  在 *耗用* 租使用者分鐘數資料庫之後是       |
|科克群島     |英國 | 是 (國家/地區)  | 在 *耗用* 租使用者分鐘數資料庫之後是        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>如何計算分鐘數計算？

請考慮下列範例。 客戶已購買 115 個音訊會議訂閱授權，而且在美國有 10 個使用者、英國有 100 個使用者，以及 5 個在美加省的使用者，全部都有指派的音訊會議訂閱授權。 所有 115 個使用者共用一組 (115 個使用者 x 60 分鐘 = 每個日曆月 6，900 個會議撥出分鐘數) ，以在任何[區域 A](audio-conferencing-zones.md)國家和地區撥打非付費號碼，不論會議召集人是授權或實際所在的位置。 例如，會場會議召集人可以撥出到任何 [區域 A](audio-conferencing-zones.md) 國家和地區，最高到分鐘數的區數限制。

- 所有超過每個日曆月 6，900 分鐘的撥出電話，都是使用我們發佈到該目的地的通訊信用額度，以每分鐘的費率計費。  (注意事項：客戶必須設定 [通訊](what-are-communications-credits.md) 信用額度，並將通訊信用額度授權指派給會議召集人。) 
- 只要客戶已設定通訊信用額度，並將通訊信用額度授權指派給會議召集人) ，所有撥出到不在 [區域 A](audio-conferencing-zones.md) 國家/地區清單中的目的地電話，都是使用我們發佈到該目的地的通訊信用額度 (以每分鐘的費率計費。

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>如何監視分鐘數我的網路使用狀況？

- 您可以在 Microsoft Teams 系統管理中心針對撥出分鐘數區監控使用方式。 在左側流覽區中，前往[分析資料&  >  **報告使用方式報告**，然後選取 **PSTN 分鐘數資料庫**。 區域 A 撥出分鐘數區會在報告中標示為「撥出電話到區域 A 國家/地區」。
- 當貴組織的撥出分鐘數使用達到 80% 和 100% 時，電子郵件通知會發送給下列系統管理員：

  - 計費系統管理員
  - 商務用 Skype 系統管理員
  - 公司系統管理員
  - 使用者帳戶系統管理員
  - 技術支援管理員
  - 服務支援系統管理員
  - 裝置系統管理員
  - 應用程式管理員
  - 授權系統管理員
  - 雲端裝置系統管理員
  - 驗證系統管理員
  - 許可權驗證系統管理員
  - Teams 通訊系統管理員
  - Teams 通訊支援工程師
  - Teams 通訊支援專員
  - Teams 服務管理員

有關通訊信用額度的其他資訊，請參閱 [通訊信用額度](what-are-communications-credits.md)。

## <a name="related-topics"></a>相關主題

- [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音訊會議的國家/地區區域](audio-conferencing-zones.md)
