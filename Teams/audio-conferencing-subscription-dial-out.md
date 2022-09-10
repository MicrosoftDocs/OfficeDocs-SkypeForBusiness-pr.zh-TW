---
title: 音訊會議撥出/通話分鐘
ms.author: heidip
author: MicrosoftHeidi
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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-mar2020
description: '[撥出] 和 [撥號給我] 分鐘優惠。 自 2019 年 12 月 1 起，每個音訊會議訂閱每個使用者每個月提供 60 分鐘給區域 A 國家/地區。'
ms.openlocfilehash: 6df0b6f2157f16da6e992d465b524a5b582e0a12
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642144"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音訊會議訂閱「撥出」/「撥打電話給我」分鐘優惠

## <a name="microsoft-teams-and-pstn-audio-conferencing"></a>Microsoft Teams 和 PSTN 音訊會議

每個音訊會議標準訂閱每個使用者每個月提供 60 分鐘，可用來撥出到任何區域 A 國家/地區的非進階號碼，如本檔所述。 此權益適用于 *音訊會議每月訂閱* 授權，且不會延伸至音訊會議每分鐘付費授權。

> [!NOTE]
> 撥出給美國和加拿大訂閱之音訊會議的撥出分鐘數集區大小取決於 *指派給* 使用者的授權數目。 例如，如果客戶有 100 個授權，其中 20 個指派給使用者，則音訊會議撥出給美國或加拿大訂閱的撥出分鐘數將會是 1200 分鐘， (指派給) 使用者的訂閱 x 20 個授權的撥出分鐘數。

> [!NOTE]
> 2019 年 11 月 30 日未針對可使用音訊會議訂閱的國家/地區，免費 [撥出期間](complimentary-dial-out-period.md) 結束，但我們目前並未提供設定通訊點數的功能。 這些特定國家是俄羅斯、南韓和臺灣。

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音訊會議「從會議撥出」&[撥打電話給我] 詳細資料

對於採用音訊會議服務的客戶，Microsoft 提供從由獲派音訊會議訂閱授權之使用者召集的會議撥出的功能。 未包含在區域 [A 國家和地區](audio-conferencing-zones.md) 清單中的國家/地區的撥出電話，會使用通訊點數每分鐘收費一次。 如果撥出電話是每分鐘計費， (超過租使用者撥出分鐘數集區的電話，或是未撥打到區域 [A 國家和地區](audio-conferencing-zones.md) 清單) 目的地的電話，通話及其相關費率是根據通話目的地而非召集人的居住國家或啟動撥出電話的會議參與者。 例如，如果您的音訊會議是由美國、法國或辛巴威的會議參與者發起，則撥打給法國這個「區域 A」國家/地區之電話號碼的音訊會議撥出電話，將會以相同的每分鐘速率計費。

|會議召集人授權使用位置 |已撥打目的地 |我可以使用撥出分鐘數集區分鐘數嗎？|我需要通訊點數嗎？|
|---------|---------|---------|---------|
|美國 |美國 |是 (區域 A 國家/地區)  |在使用租使用者分鐘數集區 *之後* 是的         |
|美國 |英國|是 (區域 A 國家/地區)  |  在使用租使用者分鐘數集區 *之後* 是的       |
|美國     |辛巴威|    否     |     [ *所有通話]* 的 [是]    |
|英國     |英國|是 (區域 A 國家/地區)  |  在使用租使用者分鐘數集區 *之後* 是的       |
|英國     |美國 |是 (區域 A 國家/地區)  |  在使用租使用者分鐘數集區 *之後* 是的       |
|英國     |辛巴威|    否     |   [ *所有通話]* 的 [是]      |
|辛巴威     |辛巴威|    否     |    [ *所有通話]* 的 [是]     |
|辛巴威     |美國 | 是 (區域 A 國家/地區)  | 在使用租使用者分鐘數集區 *之後* 是的        |
|辛巴威     |英國 | 是 (區域 A 國家/地區)  | 在使用租使用者分鐘數集區 *之後* 是的        |
|科克群島     |科克群島 |   否      |    [ *所有通話]* 的 [是]     |
|科克群島     |美國  | 是 (區域 A 國家/地區)  |  在使用租使用者分鐘數集區 *之後* 是的       |
|科克群島     |英國 | 是 (區域 A 國家/地區)  | 在使用租使用者分鐘數集區 *之後* 是的        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>如何計算分鐘集區？

請考慮下列範例。 客戶已購買 115 個音訊會議訂閱授權，且美國中有 10 個使用者、英國有 100 個使用者，以及 5 位在辛巴威的使用者，全部都已指派音訊會議訂閱授權。 所有 115 個使用者共用 (115 個使用者的集區 x 60 分鐘 = 每個行事曆月 6，900 個會議撥出分鐘數，) 將撥出電話撥打到任何 [A 區國家/地區的](audio-conferencing-zones.md)非進階號碼， *無論* 會議召集人是獲得授權或實際位置。 例如，辛巴威會議召集人可以撥出到任何 [「A 區」國家/地區，且地區](audio-conferencing-zones.md) 最多可達分鐘集區限制。

- 每個行事曆月超過 6，900 分鐘的所有撥出電話，都是以我們發佈的費率，以通訊點數計費到該目的地。

   > [!NOTE]
   > 客戶必須設定 [通訊點數](what-are-communications-credits.md) ，並將通訊點數授權指派給會議召集人。

- 只要客戶已設定通訊點數，並將通訊點數授權指派給會議召集人) ，所有未在 [「區域 A」國家及地區](audio-conferencing-zones.md) 清單中目的地的撥出電話，都會以我們發佈的費率，對該目的地的通訊點數按分鐘計費 (。

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>如何監控集區使用量的分鐘數？

- 您可以在 Microsoft Teams 系統管理中心監控撥出分鐘數集區中的使用方式。 在左側導覽中，移至 **[分析&報告**  >  **使用方式報告**，然後選取 **[PSTN 分鐘集區]**。 區域 撥出分鐘數集區會在報告中標示為「撥出至 A 區域國家/地區」。
- Email 當貴組織的撥出分鐘數集區使用量已達 80% 和 100% 時，系統會傳送通知給下列系統管理員：

  - 計費系統管理員
  - 全域系統管理員
  - 使用者系統管理員
  - 技術服務管理員
  - 服務支援系統管理員
  - Azure AD 加入裝置本機系統管理員
  - 應用程式系統管理員
  - 授權系統管理員
  - 雲端裝置系統管理員
  - 驗證系統管理員
  - 許可權驗證系統管理員
  - Teams 通訊系統管理員
  - Teams 通訊支援工程師
  - Teams 通訊支援專家
  - Teams 系統管理員

如需通訊點數的其他資訊，請參閱 [通訊點數](what-are-communications-credits.md)。

## <a name="related-topics"></a>相關主題

- [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音訊會議的國家和地區區域](audio-conferencing-zones.md)
