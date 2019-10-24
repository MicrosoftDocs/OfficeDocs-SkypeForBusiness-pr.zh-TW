---
title: Microsoft 團隊 PSTN 使用方式報告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: 瞭解如何使用 Microsoft 團隊系統管理中心的 [小組 PSTN 使用量] 報告，以取得貴組織中通話和音訊會議的使用方式的概覽。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89d33f15401d25767c905f16e38d93744d7929c3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639643"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft 團隊 PSTN 使用方式報告

Microsoft [團隊管理中心] 中的 [團隊 PSTN 使用方式] 報告可讓您在組織中進行通話和音訊會議活動的概覽。 如果您使用自己的電話運營商，您可以查看通話方案的詳細通話活動（如果您使用的是電話語音運營商），以及直接路由。

[**通話方案**] 索引標籤會顯示資訊，包括使用者在輸入和輸出 PSTN 通話中所花費的分鐘數，以及這些通話的成本。 [**直接路由**] 索引標籤會顯示您的資訊，包括 SIP 位址及呼叫開始和結束時間。 使用此報告中的資訊，深入瞭解貴組織中的 PSTN 使用量，並協助您調查、規劃及做出業務決策。

## <a name="view-the-report"></a>查看報表

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**分析] & 報告** > **使用方式報告**。 在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [ **PSTN 使用方式報告**]。
2. 在 [**日期範圍**] 底下，選取7或28天的預先定義範圍，或設定自訂範圍，然後選取 [**執行報表**]。

## <a name="interpret-the-report"></a>解讀報表

### <a name="calling-plans"></a>通話方案

![系統管理中心的通話方案 PSTN 使用報告報告的螢幕擷取畫面](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "[Microsoft 團隊系統管理中心] 中含有編號標注的 PSTN 使用狀況報告螢幕擷取畫面")

|圖說文字 |說明  |
|--------|-------------|
|**sr-1**   |您可以在過去7天、28天或您設定的自訂日期範圍中查看趨勢 |
|**pplx-2**   |每個報告都有產生的日期。 報告通常會反映來自啟用時間的24到48小時延遲時間。 |
|**3**   |X 軸是特定報表的已選取日期範圍。 Y 軸是在所選時段內的通話總數目。 <br>將游標暫留在指定日期上的點上，即可查看該日期的總通話情況。  |
|**4**   |下表提供每個通話的 PSTN 使用量細分。 <ul><li>[**時間戳記（UTC）** ] 是呼叫開始的時間。</li><li>[**顯示名稱**] 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。</li><li>[**使用者名**] 是使用者的登入名稱。</li><li>[**電話號碼**] 是已接收撥入通話通話或撥出通話電話號碼的號碼。</li><li>**呼叫類型**：撥打電話為 PSTN 輸出或撥入通話，以及撥打電話類型（例如使用者或音訊會議發出的通話）。 您可能會看到的呼叫類型包括：<br><br>**團隊使用者通話類型**<ul><li>**user_in** -使用者收到輸入 PSTN 通話。</li><li>**user_out** -使用者已發出輸出 PSTN 通話</li><li>**user_out_conf** -使用者已將兩個或多個 PSTN 參與者加入通話中，例如三向會議通話</li><li>**user_out_transfer** -使用者已將來電轉接至 PSTN 號碼</li><li>**user_out_forwarding** -使用者將呼叫轉寄至 PSTN 號碼</li><li>**conf_in** -音訊會議橋接器的撥入通話</li><li>**conf_out** -從音訊會議橋接器撥出的撥出通話通常是將 PSTN 號碼新增至會議</li></ul><br>**團隊機器人呼叫類型**<ul><li>**ucap_in** -對團隊 bot 的入站 PSTN 呼叫（例如自動語音應答或通話佇列）</li><li>**ucap_out** -來自團隊 bot （例如自動語音應答或通話佇列）的出站 PSTN 呼叫</li></ul><br><li>**呼叫為**撥打的號碼。</li><li>[**國家或地區**] 是已撥的國家或地區。</li><li>[**寄件者**] 是撥打電話的號碼。</li><li>[**從國家或地區**] 是撥打通話位置的國家或地區。</li><li>[**收取費用**] 是支付給您帳戶之通話的金額或成本。 </li><li>**貨幣**是用來計算通話成本的貨幣類型。 </li><li>[**持續時間**] 是通話的連線時間。</li><li>**國內/國際**是根據使用者的位置，告訴您通話是國內（在國家或地區內）還是國際（位於國家或地區外）。</li><li>[**通話 id** ] 是通話的通話 id。 它是呼叫 Microsoft 支援時可以使用之通話的唯一識別碼。</li><li>[ **Number type** ] 是使用者的電話號碼類型，例如免付費電話號碼的服務。 </li><li>[**國家或地區**] 是使用位置。 </li> <li>[**會議 id** ] 是音訊會議的會議 id。 </li><li>**功能**是通話使用的授權。 您可能會看到的授權類型包括：<ul><li>**MCOPSTNPP** -通訊點數</li><li>**MCOPSTN1** -國內通話方案（3000美元/1200 分歐盟方案）</li><li>**MCOPSTN2** -國際通話方案</li><li>**MCOPSTN5** -國內通話方案（120最小通話方案）</li><li>**MCOPSTN6** -國內通話方案（240最小通話方案）</li><li>**MCOMEETADD** -音訊會議</li><li>**MCOMEETACPEA** -每分鐘付款音訊會議</li></ul></li></ul> 若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。|
|**500**   |選取 [**編輯欄**] 以新增或移除表格中的欄。 |
|**6**   |選取 [**篩選**]，依使用者名稱或通話類型篩選報表 |
|**utf-7**   |選取 [**全螢幕**]，以全螢幕模式查看報告。 |
|**型**   |您可以將報表匯出為 CSV 檔案，以便進行離線分析。 按一下 [**匯出至 Excel**]，然後在 [**下載**] 索引標籤上，按一下 [**下載**] 以在準備好時下載報告。|

### <a name="direct-routing"></a>直接路由

![系統管理中心 [直接路由 PSTN 使用狀況報告] 報告的螢幕擷取畫面](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "在 Microsoft 團隊系統管理中心使用編號標注直接路由 PSTN 使用方式報告的螢幕擷取畫面")

|圖說文字 |說明  |
|--------|-------------|
|**sr-1**   |您可以在過去7天或28天的趨勢中查看報告。 |
|**pplx-2**   |每個報告都有產生的日期。 報告通常會反映來自啟用時間的24到48小時延遲時間。 |
|**3**   |X 軸是特定報表的已選取日期範圍。 Y 軸是在所選時段內的通話總數目。<br>將游標暫留在指定日期上的點上，即可查看該日期的總通話情況。  |
|**4**   |下表提供每個通話的 PSTN 使用量細分。 <ul><li>[**時間戳記（UTC）** ] 是呼叫開始的時間。</li><li>[**顯示名稱**] 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。</li><li>**Sip 位址**是接聽或撥打電話之使用者的 sip 位址。</li><li>[**電話號碼**] 是撥打電話之使用者的號碼。 </li><li>**呼叫類型**：撥打電話為 PSTN 輸出或撥入通話，以及撥打電話類型（例如使用者或音訊會議發出的通話）。 您可能會看到的呼叫類型包括：<br><br>**團隊使用者通話類型**<ul><li>**dr_in** -使用者收到輸入 PSTN 通話</li><li>**dr_out** -使用者已發出輸出 PSTN 通話</li><li>**dr_out_user_conf** -使用者已在通話中新增 PSTN 參與者</li><li>**user_out_transfer** -使用者已將來電轉接至 PSTN 號碼</li><li>**dr_out_user_forwarding** -使用者將呼叫轉寄至 PSTN 號碼</li><li>**dr_out_user_transfer** -使用者已將來電轉接至 PSTN 號碼</li><li>**dr_emergency_out** -使用者進行緊急通話</li></ul><br>**團隊機器人呼叫類型**<ul><li>**dr_in_ucap** -對團隊 bot （例如自動語音應答或通話佇列）的入站 PSTN 呼叫</li><li>**dr_out_ucap** -來自團隊 bot （例如自動語音應答或通話佇列）的出站 PSTN 呼叫</li></ul><br><li>[**呼叫**者] 是接聽通話的使用者號碼。</li><li>**開始時間（UTC）** 是呼叫連線的時間。</li><li>**邀請時間（UTC）** 是呼叫開始的時間。</li><li>**失敗時間（UTC）** 是呼叫失敗的時間。 （僅限失敗的呼叫。）</li><li>**[結束時間（UTC）** ] 是通話結束的時間。 （僅適用于成功的呼叫。）</li><li>[**持續時間**] 是通話的連線時間。</li><li>[ **Number type** ] 是使用者的電話號碼類型，例如免付費電話號碼的服務。 </li><li>[**媒體旁路**] 表示主幹是否已啟用媒體旁路 </li> <li>**SBC FQDN**是會話邊界控制器（SBC）的完整功能變數名稱（FQDN）。 </li><li>**Azure region**是用來進行信號的資料中心。</li><li>**事件種類**是通話的事件種類。 您將會看到成功呼叫成功，並嘗試失敗的通話。 </li><li>**最終 SIP 代碼**是通話結束的程式碼。</li><li>**最終的 Microsoft 子代碼**是指示發生的特定動作的程式碼。</li><li>**最終 sip 片語**是 sip 代碼與 Microsoft 子代碼的描述。</li><li>**COORELATION ID**是呼叫 Microsoft 支援時可以使用之通話的唯一識別碼。</li></ul> 若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。|
|**500**   |選取 [**編輯欄**] 以新增或移除表格中的欄。 |
|**6**   |選取 [**全螢幕**]，以全螢幕模式查看報告。 |

## <a name="related-topics"></a>相關主題

- [團隊分析和報告](teams-reporting-reference.md)