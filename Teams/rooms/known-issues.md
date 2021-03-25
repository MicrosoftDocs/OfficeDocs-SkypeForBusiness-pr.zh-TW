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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 系統管理員可以瞭解 Microsoft Teams 會議室的已知問題清單，包括更新、使用者介面、硬體、限制和預期行為。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02e7d2411fa1d8a86fe20dcab3013be758f22a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117531"
---
# <a name="known-issues"></a>已知問題 
 
本文列出 Microsoft Teams 會議室的已知問題，並按功能區域列出。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 問題標題 |  行為 \/ 症狀 | 已知的因應措施 | KB 文章 |
|  ---        |      ---             |   ---            | --- |
| 應用程式未啟動 |  更新至應用程式版本 4.4.41.0 之後，系統會引導至黑色螢幕，或幾分鐘後進入登入畫面。 | 請遵循 Microsoft Teams 會議室應用程式中更新至 [版本 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) 後無法啟動的步驟來修正此問題。  | 無 |
|  SfB 會議內容共用未顯示全螢幕         |    在商務用 Skype 會議中，使用高 DPI 設定顯示會議室的會議室可能會遇到共用至會議的內容未在會議室顯示器前方顯示全螢幕的問題。 這是因為 Windows 10 遠端桌面通訊協定或 RDP (API) 問題。 | 使用 `<WinRTRdpEnabled>` XML 設定來停用 Windows 10 RDP API 以解決此問題。 若要停用，您必須將值指定為 `false` 。 詳細資訊，請參閱使用 [XML 設定檔管理主控台設定](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。 | 無 |
|  應用程式已過期         |    Microsoft Teams 會議室主控台顯示「系統組態已過期」錯誤。                |   [使用 Microsoft Teams 會議室修復工具](recovery-tool.md)             |  無 |
|  裝置更新至不支援的 Windows 10 版本   |    Windows 10 裝置從版本 1803 更新為版本 1809，但不支援。 支援的版本為 1903。 |   如果 [DeferFeatureUpdatesPeriodinDays](/windows/deployment/update/waas-configure-wufb) 的群組原則或 MDM 設定設為最多 365 天，可讓您將功能更新延後指定的天數，則可能發生此情況。 <br><br> Microsoft Teams 會議室不支援 Windows 10 版本 1809，而支援版本 1903。 不過，自 2020 年 3 月 27 日，版本 1809 已經超過 365 天。 如果未變更此設定，Windows 會嘗試安裝版本 1809，這可能會導致 Microsoft Teams 會議室發生問題。<br><br>若要避免這種情況， **請移除** 任何群組原則或 MDM 設定以延後更新。 這可讓 Windows 更新至最新、支援的作業系統版本。 <br><br>**重要** 必須移除群組原則或 MDM設定， (未設定) 且未設為 **0。** 如果策略設為 0，Windows 會採用可能不受支援的最新可用版本。 |  無 |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>使用者介面 

| 問題標題 |  行為 \/ 症狀 | 已知的因應措施 | KB 文章 |
|  ---        |      ---             |   ---            | --- |
|虛擬鍵盤遺失   | 當您需要在 Microsoft Teams 會議室中輸入資訊時，虛擬鍵盤不會顯示。 此問題會發生在 Windows 10 版本 1903 中。 | 透過 Windows Update 安裝適用于 x64 型系統的 Windows 10 版本 1903 的 2020-04 累加更新。  | 無 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬體

| 問題標題 |  行為 \/ 症狀 | 已知的因應措施 | KB 文章 |
|  ---        |      ---             |   ---            |   --- |
| 未偵測到監視器 | 當您在 Surface Pro (2017) 裝置上執行 Microsoft Teams 會議室時，不會偵測到監視器。 |  按住 Surface Pro 電源按鈕 20 秒以上。 當您這麼做時，裝置會重新開機並清除圖形緩存。 |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制和預期行為

***

Microsoft Teams 會議室不支援 HDCP 輸入，因為已觀察此輸入會造成 HDMI 輸入功能與視 (音訊) 。 請小心確保連接至 Microsoft Teams 會議室的開關已關閉 HDCP 選項。 

***

如果您希望會議室前方的顯示器自動切換到使用中的視 (例如當來源從待命模式喚醒時) 則必須符合某些條件。 這項功能是選擇性的，但 Microsoft Teams 會議室軟體支援此功能，提供基礎硬體支援此功能。 作為會議室前顯示器的消費者電視需要支援消費者電子 (CEC) HDMI 功能。  視選取的固定座或主機 (可能不支援 CEC，請參閱製造商支援檔) ，可能需要來自Crsron的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 Exron 的 [Exron HD CTL 100](https://www.extron.com/article/hdctl100ad) 控制器，才能啟用想要的行為。 

***

一直使用有線的 1-英鎊網路連接，以確保您擁有所需的頻寬。 

***

如果您的 Microsoft Teams 會議室裝置失去對網域的信任，您將無法驗證至裝置並開啟設定。 例如，如果您在加入網域之後從網域移除 Microsoft Teams 會議室，信任會遺失。 解決方法是使用本地系統管理員帳戶登入。 
***
Microsoft Teams 會議室是多視窗應用程式，需要會議室前方的顯示器連接到裝置 HDMI 埠，應用程式可以正確運作。 請確定您連接了 HDMI 顯示器，或是使用虛擬 HDMI 插頭進行測試，但尚未購買顯示器。
***
<a name="See"> </a>  
## <a name="see-also"></a>另請參閱

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 會議室](rooms-manage.md)