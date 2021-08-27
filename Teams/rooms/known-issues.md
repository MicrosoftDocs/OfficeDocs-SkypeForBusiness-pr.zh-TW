---
title: 已知問題
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 系統管理員可以瞭解適用于使用者的已知問題Microsoft Teams 會議室，包括更新、使用者介面、硬體、限制和預期行為。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: adf3b0fb7642b4a9774459527af304fe33167352
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578317"
---
# <a name="known-issues"></a>已知問題 
 
本文將根據功能區域列出Microsoft Teams 會議室已知問題。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 問題標題 |  行為 \/ 症狀 | 已知的因應措施 | KB 文章 |
|  ---        |      ---             |   ---            | --- |
| 應用程式未啟動 |  更新至應用程式版本 4.4.41.0 之後，系統會引導至黑色螢幕，或幾分鐘後進入登入畫面。 | 請遵循更新[Microsoft Teams 會議室 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update)之後，應用程式無法啟動中的步驟來修正此問題。  | 無 |
|  內容共用後的會議音量較低         |   Microsoft Teams 會議室 20H2 體驗Windows 10裝置透過室內 HDMI 共用內容後，媒體和會議音量降低。 這是因為 20H2 Windows 10問題所導致。 | 此問題的修正程式可在應用程式版本 [4.9.12.0 中提供](/microsoftteams/rooms/rooms-release-note#49120-7282021)。 | 無 |
|  應用程式已過期         |    主機Microsoft Teams 會議室顯示「系統組態已過期」錯誤。                |   [使用 Microsoft Teams 會議室修復工具](recovery-tool.md)             |  無 |
|  裝置更新為不支援的版本Windows 10   |    Windows 10從版本 1803 更新至版本 1809，但不支援此裝置。 支援的版本為 1903。 |   如果 [DeferFeatureUpdatesPeriodinDays](/windows/deployment/update/waas-configure-wufb) 的群組原則或 MDM 設定設為最多 365 天，可讓您將功能更新延後指定的天數，則可能發生此情況。 <br><br> Windows 10版本 1809 不支援Microsoft Teams 會議室版本 1903。 不過，自 2020 年 3 月 27 日，版本 1809 已經超過 365 天。 如果未變更此設定，Windows嘗試安裝版本 1809，這可能會導致Microsoft Teams 會議室。<br><br>若要避免這種情況， **請移除** 任何群組原則或 MDM 設定以延後更新。 這可讓Windows更新至最新、支援的作業系統版本。 <br><br>**重要** 必須移除群組原則或 MDM設定 (未設定) 且未設為 **0。** 如果策略設為 0，Windows會採用可能不支援的最新可用版本。 |  無 |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>使用者介面 

| 問題標題 |  行為 \/ 症狀 | 已知的因應措施 | KB 文章 |
|  ---        |      ---             |   ---            | --- |
|虛擬鍵盤遺失   | 當您需要在 Microsoft Teams 會議室 中輸入資訊時，虛擬鍵盤Microsoft Teams 會議室。 此問題會發生在 Windows 10版本 1903 中。 | 透過更新為 x64 型系統的 Windows 10 1903 版本安裝 2020-04 累加更新Windows更新。  | 無 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬體

| 問題標題 |  行為 \/ 症狀 | 已知的因應措施 | KB 文章 |
|  ---        |      ---             |   ---            |   --- |
| 未偵測到監視器 | 當您在 Microsoft Teams 會議室 2017 Surface Pro (裝置上執行) 時，系統不會偵測到監視器。 |  按住電源Surface Pro按鈕 20 秒以上。 當您這麼做時，裝置會重新開機並清除圖形緩存。 |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制和預期行為

***

Microsoft Teams 會議室不支援 HDCP 輸入，而 HDCP 輸入已觀察會導致 HDMI 輸入功能與視 (音訊) 。 請小心確保已連接到 Microsoft Teams 會議室的開關已關閉 HDCP 選項。 

***

如果您希望會議室前方的顯示器自動切換到使用中的視 (例如當來源從待命模式喚醒時 (則) 必須符合某些條件。 這項功能為選擇性，但Microsoft Teams 會議室支援，但基礎硬體支援此功能。 做為會議室前顯示器的消費者電視需要支援消費者電子 (CEC) HDMI 功能。  視選取的固定座或主機 (可能不支援 CEC，請參閱製造商支援檔) ，可能需要來自Crsron的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 [Exron HD CTL 100](https://www.extron.com/article/hdctl100ad) 的控制器，才能啟用想要的行為。

此外，用來做為會議室前方顯示器的消費者電視可能會導致軟體的穩定性Microsoft Teams 會議室問題。 這是因為備用模式不一致的實現、使用中的視音訊來源選擇，以及將錯誤的 EDID 資訊Microsoft Teams 會議室裝置。 已知症狀是會議室顯示器前方出現黑色/灰色畫面，或主機Microsoft Teams 會議室從待命狀態喚醒後無法回應。  如果使用消費者電視時發生問題，我們建議您從 FSR 影片產品群組安裝可配置的 EDID 控制器或 EDID 模擬器，例如來自 Cresron 或[DR-EDID Emulator 的](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143) [HD-RX-201-C-E。](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E)

***

一直使用有線的 1-英鎊網路連接，以確保您擁有所需的頻寬。 

***

如果您的Microsoft Teams 會議室失去對網域的信任，您將無法在裝置中驗證並開啟設定。 例如，如果您在網域加入Microsoft Teams 會議室移除網域，信任會遺失。 解決方法是使用本地系統管理員帳戶登入。 
***
Microsoft Teams 會議室是多視窗應用程式，需要會議室前方的顯示器連接到裝置 HDMI 埠，應用程式可以正確運作。 請確定您連接了 HDMI 顯示器，或是使用虛擬 HDMI 插頭進行測試，但尚未購買顯示器。
***
<a name="See"> </a>  
## <a name="see-also"></a>另請參閱

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 會議室](rooms-manage.md)
