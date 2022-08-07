---
title: 健康情況與使用方式報告
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 報告有關健康情況與報告使用方式的節點資料
f1keywords: ''
ms.openlocfilehash: 87a04860a69799bf00492691dc24498076bd4924
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271428"
---
# <a name="health-and-usage-reports"></a>健康情況與使用方式報告

報告節點包含有關您的 Microsoft 受管理會議室和服務深入解析之健康情況和使用方式的資料。 **概觀** 會呈現您會議室的全租使用者健康情況趨勢。 [ **健康情況]** 索引標籤會顯示一份含有其對應健康情況資料的會議室清單。 根據行事曆資訊和通話品質資料的會議室使用方式會顯示在 [ **使用** 狀況] 索引標籤底下。

## <a name="navigating-reports"></a>流覽報表

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

概觀區段提供會議室管理重要層面的圖形化表示。 圖表會根據選取的時間範圍或選取的群組而有所變更。 若要變更時間範圍，請按一下下拉式功能表。

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

若要變更群組，請按一下橫幅中的群組選取下拉式功能表。

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>依類別購買票證

環圈會顯示所選時間範圍的總票證，而群組 (預設值為七天，所有群組) 。 票證會以其主要類別表示：音訊、顯示器、周邊、連線、版本設定和客戶回報。

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

選取時會顯示該類別票證詳細檢視的飛出視窗。

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

在飛出視窗中，您可以透過子類別來篩選票證清單，方法是選取圓圈的個別部分。 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

若要向後流覽，請按一下環圈，或按一下左上角的軌跡。

若要在此清單檢視中流覽至特定票證，請按一下 **支援票證** 庫底下的連結。

### <a name="ticket-history"></a>票證歷程記錄

票證歷程記錄圖表顯示在指定期間內指派給您或 Microsoft 的事件比較。

> [!NOTE]
> 如果某一天中的票證變更擁有者，凡是擁有當日大部分作業的人員，都會將票證計入其中。 例如，如果您在一天中早期將票證指派給 Microsoft，票證會計算為當天 **指派給 Microsoft** 。

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>健康情況歷程記錄

此圖表顯示 [健康情況] 區段中的平均健康情況 (定義) 租使用者中所有會議室，以及所有 MMR 客戶每天的平均健康情況。 您可以檢視最多 90 天的平均健康情況。

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>最可靠/最不可靠的會議室

根據健康情況，兩個表格顯示最可靠及最不可靠的會議室。 針對完整清單檢視，選取 [健康情況]，然後依 [健康情況] 欄排序清單。

### <a name="rooms-history"></a>會議室歷程記錄

提供在服務中註冊之會議室的歷史檢視，並提供在相同時間段內健康或不受監視之聊天室的比較級檢視。

## <a name="health"></a>健康

若要流覽至所有會議室的 [健康情況報告]，請選取 [報告]，然後選取 [  **健康情況]**。

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

健康情況分數是專為表面會議室設計的計量，最有可能造成使用者挫折。 房間在一天中可能會健康或不健康。 如果票證或多張票證在非維護時間期間影響會議室超過 20 分鐘， (當地時間上午 5 點到晚上 9 點，這會被視為不健康) 。 例如，如果票證是在上午 5：00 開啟，但在上午 5：15 關閉，則會議室仍會視為健康情況。 但是，如果第二張票證是從上午 09：00 到上午 9：10，則該房間會視為當天不正常的。 同樣地，如果票證是從上午 5：00 到上午 5：21，則該票證會視為不正常的一天。

> [!NOTE]
> 每天上午 12：00 UTC 時，會匯總一天的健康情況一次。 對於接近國際日期線的客戶，健康情況匯總可能會在工作日接近中間時發生。

> [!NOTE]
> 正在上線的會議室會隱藏在 [健康情況] 索引標籤的會議室清單中，而不會計入租使用者的平均健康情況。

按一下此檢視中列出的聊天室會顯示更多詳細資料。

橫條圖會顯示每天的門票數量。 在該天開啟的門票會以藍色顯示。 在個別日期之前開啟的門票會以橘色顯示。 按一下圖形上的某一天，即可篩選圓形圖和表格至相關的票證。 若要反轉篩選，請使用軌跡流覽或按一下圖形。

票證分類會以環圈圖表示。 與此互動會篩選時程表圖形和表格。 若要反轉篩選，請使用軌跡流覽或按一下圖形。

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

會議影響檢視會顯示已排程的會議，期間會開啟具有嚴重性為「重要」或「重要」的票證。 此檢視的目的是提供參與者可能遇到問題的會議大致。

會議影響檢視會顯示已排程的會議，期間會開啟具有嚴重性為「重要」或「重要」的票證。 此檢視的目的是提供參與者可能遇到問題的會議大致。

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

[設定] 索引標籤會顯示會議室的中繼資料，例如硬體資訊、裝置設定、BIOS 資訊、應用程式設定和位置。

## <a name="usage"></a>使用

若要檢視所有會議室的使用方式報告，請選 **取 [報告>使用量]**。

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

標題提供一些深入解析：

- 租使用者中的會議室總數
- 多少人沒有預約任何預定的會議，無論是離線或線上
- 租使用者中會議室使用率的百分比
- 透過 Exchange 預定的會議總數
- 包含 Skype 或 Teams 連結的預定會議百分比
- 會議室參與的總通話數目
- 所有通話都以「良好」品質分類到所有通話的匯總通話效能分數。 

標題計量下方是具有對應計量的會議室表格。 選取會議室以檢視更多使用詳細資料。 下表說明資料表中的計量。

|列|描述|
|---|---|
|利用|會議室在所選期間的上班時間內預約的時間百分比。 前。 時間週期設定為 7 天。 超過預約會議室 32/40 小時之表示的 80% 使用率|
|已線上預約|已預訂的會議中，已啟用 Teams 的百分比。 前。 已預約 10 個會議。 其中，8 個具有 Teams 連結。 已預約線上 = 80%|
|排定的會議|會議室中排程的會議絕對數目|
|總通話數|以參與者身分撥打會議室的通話絕對數目。|
通話效能|有「良好」評等的通話百分比。 系統會評估每個通話，並收到良好、不佳、未知的評分。 此計量是從良好通話/總通話量計算|

使用量是以會議室裝置的當地時間午夜 (00：00) 月底計算。 使用率是根據當天預定的會議時間總計除以 8 小時來計算。

## <a name="usage-details-of-a-room"></a>會議室的使用詳細資料

按一下清單檢視中的會議室會提示含有更深入資訊的飛出視窗。 飛出視窗的 [使用率] 索引標籤底下有一個圖表，顯示過去五個工作天的使用時間。 每天有兩個長條：藍色代表預定的會議時間;紫色代表 Teams/Skype 已啟用的會議排程時間。 最後會計算過去五個工作天的平均會議預約和持續時間。

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

[ **通話]** 表格顯示會議室參與 Teams 通話的會議。 會議室音訊品質只會評估會議室，而非所有參與者。 若要檢視特定通話中所有參與者的通話品質，請按一下 [開始時間] 來選取通話。

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

若要檢視會議室的串流詳細資料，請按一下 [會話開始時間]。
