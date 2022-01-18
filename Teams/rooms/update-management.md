---
title: Microsoft Teams 會議室更新管理
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 主動監控您的會議室。
f1keywords: ''
ms.openlocfilehash: 763eece92a65aa8ca70728854a1af8970fd13d25
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767466"
---
# <a name="update-management"></a>更新管理 
現代化的會議室配備Microsoft Teams 會議室裝置和其他周邊裝置，例如相機、麥克風或喇叭，以及可能更多裝置，以建立全面且有效的會議體驗。 不同類型的 OEM 設備可提供所需的確切組織體驗;不過，必須持續使用軟體與固件維護。  

Managed Services for Microsoft Teams 會議室保證貴組織中每個會議室都會維持在建議層級，以提供隨時就緒且正常運作的會議室。 Microsoft 的目標是使用智慧和自動化功能，降低營運員工的複雜性和作業。 疑難排解或診斷會儘快執行。 

## <a name="transitioning-a-device-to-managed-services"></a>將裝置轉換為 Managed Services 
會議室裝置上機至 Managed Services 時，通常會有變更管理歷程記錄與練習，這一點與我們的指引不同。  

- 若要從 Managed Services 獲益，您必須轉換 Managed Services 產品群組下所有更新的變更管理。
- 變更管理的多個來源會影響事件 SLA，因為如果會議室發生事件，將會重新開機探索和補救。
- Microsoft 已實施控制措施和檢查，以執行可能不同組織不同的政策，以及特殊情況下的介入能力。
- 最後，會議室裝置會更新為一般標準，但因特定硬體安裝問題而例外。  

## <a name="transitioning-devices-basic-readiness-checks"></a>轉場裝置：基本準備檢查 
大多數的意外失敗都是由基礎影像中變更而產生，而變更管理歷程記錄不確定。 

建議使用下列簡單的準備檢查：  

- **基本影像**：基本影像必須來自特定的 OEM。 如果裝置過去已重建，且在一般工作上顯示意外失敗或行為，則必須還原基本影像。 我們可以提供協助，但無法遠端重建會議室裝置，因此您需要當地網站技術人員。  
- **基本作業系統，版本：** 基本作業系統與版本必須符合Microsoft Teams 會議室需求。 如果沒有，則必須在上機時加以修正。 Microsoft Teams 會議室通道維護選項Windows 10 IoT 企業版或Windows 10 企業版 SKUS Semi-Annual SKUS。 詳情請參閱 [官方的國指引](rooms-lifecycle-support.md#windows-10-release-support) 。

## <a name="readiness-checks"></a>準備狀態檢查   
接收受管理服務更新有幾個先決條件： 

|軟體 |指導方針 |
| :- | :- |
|Logitech 同步服務  |應在 Logitech 會議室裝置上安裝並運作。 除非封鎖，否則系統會自動從更新Windows同步處理服務。 您也可以安裝完整的同步套件。 |
|Windows OS 更新 |應保持啟用，且不會重新導向至 WSUS，也不會從網路角度封鎖。 不應使用 GPO 或 MDM 策略來管理作業系統更新。 |
|Microsoft Store更新   |應該關閉。 Managed Services 會關閉市集中更新 ，如果發現已開啟。 |
|防毒軟體 |如果您在這些裝置上經營 AV 軟體，您應該確保 AV 已針對 Teams 和 dll Skype排除。 請參閱這裡以進一步查看詳細資料。 |
|其他軟體 |其他軟體 ，例如協力廠商遠端桌面檢視等，應該使用 Managed Services 進行校閱，以排除其負面影響。 |
|其他變更管理|可能會干擾涵蓋的更新，且不應引入。 |

## <a name="managed-updates--how-it-works"></a>受管理更新 – 其運作方式 
管理更新的主要方式有兩種：  

- **自動管理**：根據 Managed Services 評定，更新會安裝在會議室裝置中。 我們產品群組中管理的更新不需要介入。
- **已驗證響** 鈴：設定響鈴系統以預覽特定裝置上的更新，這樣您即可監控更新，而不需要相關的支腳作業。 在廣泛推出之前，響鈴設定提供額外的適當注意。  

### <a name="automatically-managed"></a>自動管理

如果您選擇自動管理，則不需要針對您的更新執行任何動作。 不過，您應該查看受 Managed Services 支援的目前更新組合。 產品群組不斷取得新的新增功能，而我們優先處理最頻繁且影響最大的更新，以確保您的房間穩定性。 查看本文 (「更新管理」區段) 清單，以規劃貴組織所需的任何其他變更管理。  

**建議：** 請勿在您自己的任何受管理裝置上安裝受管理服務涵蓋的更新。 如果您遇到任何問題，請在入口網站中報告事件。

### <a name="ring-validation"></a>響鈴驗證

選擇響鈴驗證時，請查看下列章節，瞭解響鈴在 Managed Services 中如何工作，以及可供貴組織自訂的選項。 即使使用響鈴驗證，Managed Services 還是會嘗試確保會議室不會在建議更新時到期。 根據情況，會議室可能會收到「趕上」更新，以確保其符合受管理的服務建議。  

 在入口網站首頁和 Managed Services 檔中查看公告，因為產品群組中會提供新的軟體和固件類型。 由於 Managed Services 專家每天會在我們的裝置產品群組中審查更新版本，因此他們會根據需求解決特定問題並針對更新進行目標更新。  


### <a name="scheduling"></a>排程 
系統根據會議室中的設備，以及若未符合適用軟體與固件的 Managed Services 標準，為會議室排程受管理更新。  

- 為了協助我們的客戶符合變更管理需求，更新部署從星期三開始在分段圈中。 如果需要重大更新，我們會忽略此排程，並儘快發佈更新。 

- 更新會依據特定聊天室中的需要排序。 
- 如果您有設定響鈴來驗證更新，更新會透過響鈴順序進行。 
- 如果我們根據您的情況判斷會議室穩定性已改善，新更新可能會取代已排入佇列的更新。  
- 更新一般會在我們的夜間維護時段期間 ，即上午 **12：00 – 上午 5：00** 會議室期間進行，以避免任何干擾。 

## <a name="microsoft-teams-room-app-update-lifecycle-policy"></a>Microsoft Teams會議室應用程式更新週期政策 
如果版本在 12 () 個月的生命週期中過期，或自該版本之後發行超過兩個更新，則所有支援均會結束。 接著，客戶必須更新至支援的版本。 請參閱應用程式[Microsoft Teams 會議室支援 - Microsoft Teams |Microsoft Docs](rooms-lifecycle-support.md)的詳細服務描述。 

為了在所有受管理聊天室中維持統一的標準，並讓我們有效率地找出熱門問題，我們會根據支援與訂閱服務條款與條件，支援及部署兩種最新的主要或次要發行 (N、N-1) 。. 我們會自動將不符合規範的會議室更新為最新狀態，並在必要時忽略更新環。 

N-1 原則也適用于協力廠商軟體。  

## <a name="update-management-experience-walk-through"></a>更新管理體驗的流覽  
若要查看更新，請登入 Managed Services 入口網站並流覽至更新頁面。 

![替代文字1](../media/update-management-001.jpg) 


更新窗格會顯示會議室更新管理高層級概觀，並包含下列選項卡： 

- **更新**：Managed Services 透過貴組織進行編排的軟體或固件更新。  
- **會議室**：會議室的選項卡提供每個房間和鈴聲的視圖。 
- **響** 鈴：顯示貴組織會議室的響鈴的響鈴。 





### <a name="updates"></a>更新  

此視圖會顯示租使用者的相關更新及其各自的狀態。 若要查看不再啟用的過去更新，請選取包含 **過去更新的** 切換至開啟。  



任何更新都可以在下列其中一種狀態： 

|地位 |描述 |
| :- | :- |
|計畫 |已針對給定響鈴中的會議室排程更新。 請記住，更新只會在進度到達會議室的響鈴後顯示排程。 例如，如果新更新位於暫存圈中，則只會在暫存環中顯示已排程的會議室。 其他響鈴會維持「不需要」狀態，直到更新進度到該響鈴。    |
|進行中 |更新正在進行中，而個別的響鈴會顯示狀態。 此狀態會顯示整個響鈴狀態，因此，如果更新適用于租使用者中暫存圈中的單一聊天室，則更新會進入「進行中」狀態，直到到達執行環。    |
|已完成失敗 |更新已完成所有已配置的響鈴，但至少有一個聊天室失敗。 |
|完成 |更新已完成所有已配置的響鈴，並成功安裝在所有適用會議室。 |
|廢棄 |更新已停用。 進一步部署已暫停。 這是一般情況，因為更新已由新版本取代。  |
|暫停 |更新已暫停狀態。  |
|不為必填專案 |更新尚未評估會議室，或不適用於會議室。  |

### <a name="rooms"></a>房間  

"會議室" 選項卡會顯示租使用者中所有的會議室，以及它們所屬的響鈴。  



![替代文字2](../media/update-management-002.jpg) 



若要設定聊天室應該屬於哪個響鈴：  

1. 按一下會議室以顯示詳細視圖。  
1. 在 [響鈴」 下，按一下 [變更」 按鈕。  
1. 選取會議室所屬的響鈴。  
1. 按一下 [指派。  

詳細會議室視圖會在 「更新」節點下顯示相關的更新及其狀態。  


![替代文字3](../media/update-management-003.jpg) 

### <a name="rings"></a>環  

響鈴是用來降低部署功能更新所衍生問題的風險。 這麼做是逐步將更新部署到整個網站。 每個響鈴都應該有會議室Microsoft Teams清單，以及對應的推出排程。 定義環通常是一次事件 

 (不常) ，但 IT 應不定期重新檢查這些群組，以確保順序仍然正確。  

「響鈴」選項卡會列出租使用者中所有的響鈴。 有三個預先配置的環：  

**分期**  

將會議室指派給暫存環，這是您的測試資料。 所有新更新都會先在這裡推出。 一般而言，您一般會想要確保您的暫存環代表環境中各種裝置類型的會議室。 如果有特定類型的會議室，其配置不常見或有看到問題的歷程記錄，請考慮在暫存中代表它們。

**一般**  

根據預設，所有會議室都位於此響鈴中。 整個企業中使用的大部分會議室裝置屬於這個類別。 

**行政**  

此群組應包含您最高調的會議室，您希望主動將干擾降到最低。 一個很好的範例是大型會議室，用於執行會議或大型小組會議。 

### <a name="specifying-rollout-timeline"></a>指定推出時程表 

更新不能超過 60 天才能完成所有響鈴。  

|**參數** |**解釋** |
| :- | :- |
|<p> </p><p>延後期間 </p>|<p>一旦更新以第一個響鈴開始，延遲期間即為在此響鈴上啟動更新前數天的延遲。  </p><p> </p>|
|<p> </p><p>推出持續時間  </p><p> </p>|<p>更新在此響鈴開始後，就是在此響鈴中部署的時間。 例如，如果持續時間為 5 天，一旦更新在此響鈴上開始，它會部署超過 5 天至此響鈴中的會議室。 </p><p> </p>|
|<p> </p><p>測試期間 </p>|<p><p>在響鈴上一次，測試/驗證響鈴更新的天數。 測試期間在推出完成後開始，一旦完成，更新會移至下一個週期。 </p><p> </p>|
|<p> </p><p>完成時間 </p>|<p> </p><p>「完成時間」欄會指出此環 (推出期間 + 測試期間) 總天數。  </p><p> </p>|
|<p> </p><p>總時間 </p>|<p> </p><p>底部的是「合計」列，表示從第一個響鈴到最後一個響鈴完成更新需要多久時間。 </p><p> </p><p> </p>|

### <a name="creating-custom-rings"></a>建立自訂環 



1. 流覽至 「響鈴」定位點。  
1. 按一下 [新增響鈴」。  
1. 指定此響鈴接收更新的順序，其中第一個為 1，最後一個為 9。  
1. 為這個響鈴命名。  
1. 如果需要，請提供描述。  
1. 指定更新將在此響鈴中推出天數。  
1. 指定測試期間。  
1. 按一下 [提交。  


> [!NOTE]
> 「其他響鈴所設定的日子」是更新在所有響鈴之間完成的總天數。 「剩餘天數」表示此響鈴完成 *的最大* 天數。 「以天計算推出期間」和「測試期間以天計算」的總和不能超過此金額。  



**編輯鈴聲** 


1. 流覽至 「響鈴」定位點。  
1. 按一下要編輯的鈴聲。  
1. 按一下 [編輯響鈴」。  
1. 如有需要，編輯推出和測試的天數。 


**刪除鈴聲** 

1. 流覽至 「響鈴」定位點。  
1. 按一下要刪除的鈴聲。  
1. 按一下 [刪除響鈴」。  



> [!NOTE]
> 無法刪除預設響鈴。  



**移動會議室** 

將會議室從一個鈴聲移動到另一個鈴聲的方法有兩種： 



1. 流覽至 「響鈴」定位點。  
1. 按一下您想要移動會議室的響鈴  
1. 按一下 [移動會議室」。  
1. 在 「會議室清單」中選取您想要移動的會議室。  
1. 選擇選取的會議室會移至下拉拉下拉的靶圈。  
1. 按一下 [移動會議室」。  

**或**

1. 開啟要移動會議室的會議室詳細資料， (事件、會議室或更新 ->會議室) 。   

1. 按一下 [更新」 Tab。  
1. 在 [已指派的響鈴」 下，按一下 [變更」  
1. 從下拉清單中選擇新的響鈴。  
1. 按一下 [指派」。 


## <a name="managed-updates-visibility-and-control"></a>受管理更新：可見度與控制  
受管理服務會協調整個組織的更新。 不過，您擁有可進行介入的可見度與控制權。如果需要的話。 方法有： 



- 如果更新失敗，系統會自動與 Microsoft Managed Service Operations 小組產生票證。 營運小組會採取步驟以補救失敗，並在必要時吸引您參與。  
- 如果您看到導致問題的更新，您可以使用暫停按鈕 **暫停更新。** 按下暫停按鈕會建立作業中心調查的票證。 請務必在暫停更新時提供詳細資料，協助加快事件回應。  
- 如果您看到聊天室中的更新失敗，而且您更正了網路中斷等合理原因，您可以使用重試所有失敗按鈕來 **重試更新。**  
- 您可能會在緊急情況下決定更早提供更新。 在這種情況下，您可以使用強制 **更新按鈕。** 使用強制更新選項時，您可以選擇立即強制更新，或在會議室旁邊可用時強制更新。  



<!--![alt text4](media/update-management.004.jpg)-->  

> [!NOTE]
> **我們不建議將「強制更新」** 做為一般更新管理策略。 如果您推送仍在驗證通過中的更新，可能會遇到我們已經知道的問題。 在這種情況下，這類聊天室的事件解決方式會盡力而為。  

- 此外，為了確保良好的變更管理作法，我們會記錄服務內部的每一個強制更新。 未來，我們預期您也能看到這項功能。 



<!--![alt text5](media/update-management.005.jpg) 


## Managed updates: FAQS 
1. **An update was announced, but I don’t see it on my Updates tab.** 

Updates roll out through our update rings. It won’t display in your tab until the update has passed the staging ring. 



2. **Will my new rooms automatically get updated?** 

Yes. We catch up with any new rooms on the necessary updates. 
**


3. **What if I have an Anti-virus running? Do I need to add exclusions?** 

Suppose you are using an anti-virus or just started using a new anti-virus. In that case, it might cause failures to launch meetings in the room console by interfering with the launch of related software libraries and executables from Teams or Skype for Business. Please contact our support team to get assistance on this issue. 

4. **I reimaged a room. Will the updates automatically get installed?** 

Unfortunately, not at this time. Previous updates need to be manually reinstalled. We are working on a feature to address this scenario. 

5. **I see an update failed. What action should I take to make it successful?** 

Our 24/7 operations team troubleshoot all update failures and will contact you if you need to take any action.  

6. **What updates can we force?** 

Any and all active updates can be forced. 

7. **When is my update starting?** 

Staging rings start on Wednesday. We are making improvements to the portal so you can see what day each of your rings starts depending on your configuration. If a critical update is required, we will bypass this schedule and release the update as soon as it’s available. -->
