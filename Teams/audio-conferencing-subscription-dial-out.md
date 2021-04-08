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
description: 撥出和撥打我通話分鐘數權益。 自 2019 年 12 月 1 日起，每個音訊會議訂閱每個月會為 A 區國家/地區提供每個使用者 60 分鐘的使用時間。
ms.openlocfilehash: effd0794a554288634af1634bcf7417050ad16b9
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617765"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音訊會議訂閱「撥出」/「撥入電話給我」分鐘權益

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Microsoft Teams 和商務用 Skype PSTN 音訊會議

每個音訊會議訂閱每個月為每個使用者提供 60 分鐘，可用來撥入任何 A 區國家/地區中的非付費號碼，如本檔所述。 您的租使用者撥出分鐘數庫大小是根據已 *購買授權* 。 此權益適用于音訊會議 *每月訂閱* 授權，且不適用於音訊會議按分鐘付費授權。

> [!NOTE]
> 自 2020 年 10 月 22 日起，租使用者撥出分鐘數庫的大小是根據已購買的音訊會議訂閱授權數量。 之前，撥出分鐘數庫大小是根據指派給使用者的授權數目。 


> [!NOTE]
> 免費撥出期間並未[](complimentary-dial-out-period.md)于 2019 年 11 月 30 日結束，適用于提供音訊會議訂閱的國家/地區，但我們目前不提供設定通訊信用額度的能力。 這些特定國家/地區為俄羅斯、韓國和臺灣。

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音訊會議「從會議撥出」&「撥號給我」詳細資料

對於採用音訊會議服務的客戶，Microsoft 提供從指派音訊會議訂閱授權之使用者所組織的會議撥出功能。 撥入未包含在 [A](audio-conferencing-zones.md) 區國家/地區清單中的國家/地區通話，會使用通訊信用額度每分鐘收費。 對於每分鐘計費的 (超出租使用者撥出分鐘數庫的撥出通話，或非區域 [A](audio-conferencing-zones.md) 國家/地區清單) 中目的地的通話，通話及其相關聯的費率是根據通話目的地，而非召集人的居住國家/地區或啟動撥出電話的會議參與者。 例如，如果音訊會議撥出電話是由美國、法國或尚比亞的會議參與者啟動，則撥打到法國的電話號碼 ，即地區 A 國家/地區，將會以相同的每分鐘費率計費。 


|會議召集人授權使用位置 |已撥號的目的地 |我可以使用撥出分鐘數分鐘數嗎？|我是否需要通訊信用額度？|
|---------|---------|---------|---------|
|美國 |美國 |是 (區域 A 國家/地區)  |使用 *租* 使用者分鐘數庫後是         |
|美國 |英國|是 (區域 A 國家/地區)  |  使用 *租* 使用者分鐘數庫後是       |
|美國     |辛巴威|    否     |     所有通話 *都為* 是    |
|英國     |英國|是 (區域 A 國家/地區)  |  使用 *租* 使用者分鐘數庫後是       |
|英國     |美國 |是 (區域 A 國家/地區)  |  使用 *租* 使用者分鐘數庫後是       |
|英國     |辛巴威|    否     |   所有通話 *都為* 是      |
|辛巴威     |辛巴威|    否     |    所有通話 *都為* 是     |
|辛巴威     |美國 | 是 (區域 A 國家/地區)  | 使用 *租* 使用者分鐘數庫後是        |
|辛巴威     |英國 | 是 (區域 A 國家/地區)  | 使用 *租* 使用者分鐘數庫後是        |
|科克群島     |科克群島 |   否      |    所有通話 *都為* 是     |
|科克群島     |美國  | 是 (區域 A 國家/地區)  |  使用 *租* 使用者分鐘數庫後是       |
|科克群島     |英國 | 是 (區域 A 國家/地區)  | 使用 *租* 使用者分鐘數庫後是        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>如何計算分鐘數庫？

請考慮下列範例。 客戶已購買 115 個音訊會議訂閱授權，且在美國有 10 個使用者、英國有 100 個使用者，以及 5 位在尚比亞的使用者，全部都指派了音訊會議訂閱授權。 所有 115 個使用者共用一個 (115 個使用者 x 60 分鐘 = 每個日曆月) 的 6，900 個會議撥出分鐘數，以在任何[A](audio-conferencing-zones.md)區國家/地區撥打非付費號碼，無論會議召集人擁有授權或實際位置。 例如，在分鐘數上限內，一位位於該區的 A 區會議召集人可以撥出到任何區域 [A](audio-conferencing-zones.md) 國家/地區。

- 每一個日曆月超過 6，900 分鐘的所有撥出通話，都是使用通訊信用額度以我們發佈到目的地的費率每分鐘計費。 

   > [!NOTE]
   > 客戶必須設定 [通訊信用額度](what-are-communications-credits.md) ，並將通訊信用額度授權指派給會議召集人。

- 所有撥打到不在 [A](audio-conferencing-zones.md) 區國家/地區清單中的目的地的撥出電話，只要客戶已設定通訊信用額度，並將通訊信用額度授權指派給會議召集人 () ，即可使用我們發佈到該目的地的通訊信用額度每分鐘計費。

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>如何監控我的泳池使用量分鐘數？

- 您可以在 Microsoft Teams 系統管理中心針對撥出分鐘數庫監控使用方式。 在左側流覽中，前往 [分析&**報告使用方式**  >  **報告**，然後選取 **PSTN 分鐘數庫**。 區域 A 撥出分鐘數庫會在報告中標示為「A 區國家/地區外撥通話」。
- 當貴組織的撥出分鐘數總和使用量達到 80% 和 100% 時，電子郵件通知會寄給下列系統管理員：

  - 帳單系統管理員
  - 商務用 Skype 系統管理員
  - 全域系統管理員 
  - 使用者系統管理員
  - Helpdesk 系統管理員
  - 服務支援系統管理員
  - Azure AD 已加入裝置本地系統管理員 
  - 應用程式管理員
  - 授權系統管理員
  - 雲端裝置系統管理員
  - 驗證系統管理員
  - 許可權驗證系統管理員
  - Teams 通訊系統管理員
  - Teams 通訊支援工程師
  - Teams Communications 支援專員
  - Teams 系統管理員

有關通訊信用額度的其他資訊，請參閱 [通訊信用額度](what-are-communications-credits.md)。

## <a name="related-topics"></a>相關主題

- [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音訊會議的國家/地區與區域](audio-conferencing-zones.md)
