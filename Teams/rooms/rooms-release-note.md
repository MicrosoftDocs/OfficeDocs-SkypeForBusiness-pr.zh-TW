---
title: 適用于該版本Microsoft Teams 會議室
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
description: 系統管理員可以閱讀 Microsoft Teams 會議室 版本資訊，其中列出 Microsoft Teams 會議室 中累積Microsoft Teams 會議室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f870f746a5ff085fc997d9071ba243e43a8046b0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772724"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>適用于該版本Microsoft Teams 會議室

本文將討論在 Microsoft Teams 會議室 中累積Microsoft Teams 會議室。

## <a name="version-history"></a>版本歷程記錄

|釋放 |發佈至 <br/> Microsoft Store |
|--- |--- |
|4.9.12.0 |07/28/2021 |
|4.8.31.0 |05/12/2021 |
|4.8.25.0 |04/22/2021 |
|4.8.19.0 |04/06/2021 |
|4.7.19.0 |02/03/2021 |
|4.7.15.0 |12/11/2020 |
|4.6.23.0 |10/19/2020 |
|4.6.20.0 |09/30/2020 |
|4.5.37.0 |08/14/2020 |
|4.5.35.0 |07/23/2020 |
|4.4.63.0 |06/25/2020 |
|4.4.41.0 |05/06/2020 |
|4.4.25.0 |03/31/2020 |
|4.3.42.0 |03/02/2020 |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8)  |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Microsoft Teams 會議室功能簡介和問題解決

### <a name="49120-7282021"></a>2021 年 7 月 7 (4.9.12.0) 

此更新仲介紹：
- Microsoft Teams應用程式設定中現在提供唯一模式，因此您不需要再設定商務用 Skype帳戶。 在此模式中，以來賓使用者Teams已商務用 Skype裝置加入會議。
- 修正導致通話音量降低的 HDMI 音訊。 所有擁有應用程式建立 4.9.12.0 的裝置都會自動啟用 HDMI 音訊功能。

> [!NOTE]
> 當商務用 Skype生命週期結束時，建議您更新至Teams模式。

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021) 

此更新仲介紹：
- Windows 10 20H2 支援 

> [!NOTE]
> Cresron UC-Engine (含有「KYSKLi」) Teams 會議室的BIOS版本日期有相容性問題，系統 OEM 近期將會提供更新的驅動程式。 Windows 10 20H2 將不會提供給這些裝置。 有關版本支援Windows，請參閱版本Windows 10[支援](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="48250-04222021"></a>2021/04/22 (4.8.25.0) 

此更新仲介紹：
- 修正在 TEAMS 會議室 主機上的會議室資訊無法顯示全域通訊錄中隱藏的聊天室帳戶 (GAL) 

> [!NOTE]
> GCCH 客戶可以從手動更新裝置下載升級套件Microsoft Teams 會議室[套件](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021) 

此更新仲介紹：
- 政府社群雲端高 (GCCH) 支援Teams 會議室。 具有現有裝置Teams 會議室 GCCH 客戶可以從手動更新裝置下載版本 4.8.19.0 Microsoft Teams 會議室[裝置](manual-update.md)
- 使用 720p (加入縮放會議) 並接收參與者的視像庫
- 商務用 Skype預設模式移除的Teams失敗橫幅。 此變更支援組織移除商務用 Skype基礎結構
- Teams加入連結剖析現在可處理 Microsoft Defender Advanced Thread Protection 保管庫連結，以便順暢Teams外部連結
- 修正共用者電腦在 商務用 Skype 中設定自訂 DPI 時，會議中的共用內容縮放Windows
- 品質和可靠性修正

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021) 

此更新仲介紹：
- 品質和可靠性修正

### <a name="47150-12112020"></a>2020/12/11 (4.7.15.0) 

此更新仲介紹：

- 與會議參與者共用 HDMI 音訊Teams會議
- Cortana預覽 (語音) 
- 當會議室以出席者Teams時，防止根據音訊許可權取消靜音。 詳細資訊，請參閱管理會議中的出席者[Teams許可權](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a)。
- 從會議室主機將某人的視Teams焦點放在會議室顯示器上，並觀看焦點影片

> [!NOTE]
> Cortana語音技能適用于美國租使用者選取的音訊周邊設備。 未來將會新增其他國家/地區。 詳細資訊，請參閱Cortana[語音Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (2020/10/19) 

此更新仲介紹：

- 修正在會議內使用螢幕小鍵盤時出現白色半螢幕Teams的問題

### <a name="46200-09302020"></a>2020/09/30 (4.6.20.0) 

此更新仲介紹：

- 在會議室顯示器前面看到更多 3x3 影片庫的影片  
- 從國電啟動當地即時隱藏式字幕
- 使用直接來賓加入Teams 會議室預覽版來加入縮放 (會議) 

> [!NOTE]
> 3x3 影片庫和本地即時隱藏式字幕會透過 Microsoft Teams提供。 這些功能適用于所有Teams 會議室 4.5.37.0 及更新版本的裝置。

### <a name="45370-08142020"></a>2020/08/14 (4.5.37.0) 

此更新仲介紹：

- 在 2S Microsoft Teams Surface Hub會議
- 修正Skype安裝更新[KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351)或Windows 10 [KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709)時，商務Windows 10登錄失敗的問題

### <a name="45350-07232020"></a>2020/07/23 (4.5.35.0) 

此更新仲介紹：

- 使用直接來賓加入Teams 會議室加入 Cisco WebEx 會議
- Teams系統管理中心啟用和自動註冊
- Windows 10 1909 版本支援
- 切換至影片庫版面配置，即使內容存在時
- 虛擬舉手支援出席者及簡報者的控制項
- 會議與預設喇叭的可調整預設音量設定
- 從會議室搜尋和 (租使用者) Teams使用者

> [!IMPORTANT]
> 版本 4.5 是支援版本 1803 的Windows 10版本;未來版本將不會提供給版本 1803 Windows 10的系統。 有關版本支援Windows，請參閱版本Windows 10[支援](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="44630-06252020"></a>2020/06/25 (4.4.63.0) 

此更新仲介紹：

- 品質和可靠性修正
- 修正「更新至 4.4.41.0 後無法啟動應用程式」問題的修正程式

> [!NOTE]
> 如果您的裝置未自動更新至版本 4.4.63.0，請遵循 Microsoft Teams 會議室 應用程式更新至[版本 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update)後無法啟動的步驟來解決問題。

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020) 

此更新仲介紹：

- 應用程式的可靠性修正程式從 Windows 10開始

### <a name="44250-03312020"></a>2020/03/31 (4.4.25.0) 

此更新仲介紹：

- 新式驗證支援Exchange商務用 Skype
- 支援動態緊急電話，Teams (服務元件，並Teams響鈴) 
- 使用 XML 停用雙顯示器會議室會議外重複內容的能力
- 應用程式初始畫面
- 開啟來源軟體 (OSS) 裝置設定中的注意事項

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020) 

此更新仲介紹：

- 「商務Windows更新」的政策更新
- 修正在 Azure 監視器中顯示錯誤的裝置附隨報告

### <a name="43330-1102020"></a>4.3.33.0 (2020/1/10) 

此更新仲介紹：

- 特定配置中所看到的視窗大小調整/閃爍問題的修正程式
- 已移除協力廠商會議的日曆處理
- Cortana狀態設定已移除

### <a name="43230-12132019"></a>2019 年 12 月 13 (4.3.23.0) 

此更新仲介紹：

- 自動接聽鄰近通話和系統管理員設定以控制此
- 裝置系統管理員設定新增裝置組配置的 UI 重新啟用功能
- 會議室控制項回到主畫面
- 會議室SKU 可在 GCC
- 適用于以 Surface Pro 為基礎的 (應用程式建立的內容相機支援：4.2.4.0) 

### <a name="4240-10072019"></a>4.2.4.0 (2019/10/07) 

此更新仲介紹：

- Windows 10 1903 支援。 Windows 10 1903 更新于 App 更新後的幾天內提供
- 螢幕小鍵盤的修正程式無法可靠地顯示

### <a name="41220-08152019"></a>2019/08/15 (4.1.22.0) 

此更新仲介紹：

- 新的內容攝影機功能，讓使用者智慧地將傳統白板納入Teams會議
- 主控台 UI 的其他改良功能，以減少雜亂設定移動至新的側邊欄，該側邊欄可透過主控台上的更多功能存取
- 如果未連接本地內容纜線或內容相機未連接，則停用的共用區按鈕
- 修正了觸控式鍵盤在重新開機後第一次出現觸控式鍵盤失敗的問題
- 品質和可靠性修正

### <a name="401050-07102019"></a>2019/07/10 (4.0.105.0) 

此更新仲介紹：

- Skype會議室系統商店應用程式重新建立為「Microsoft Teams 會議室」
- Microsoft Teams 會議室主機使用者介面重新Microsoft Teams
- 主題更新：只在會議室顯示器前面保留自訂背景影像，同時將主機背景製作為中性色彩，以確保主機 UI 控制項符合色彩對比 — 協助工具需求
- 適用于電話會議/會議Teams通話控制項的通用Microsoft Teams PC/Web/Mobile 用戶端<sup>1</sup>
- 通話後通話品質Teams評<sup>等 1</sup>
- 從 PC/Web/Mobile Microsoft Teams 會議室用戶端<sup>1 2</sup><sup></sup>時，在Microsoft Whiteboard畫面前接收/Teams圖像
- 由於用戶端Windows 10相容性問題，已移除版本 1809 升級Microsoft Teams 會議室支援。 Windows 10版本 19H1 支援將會在未來版本中新增

<sup>1</sup> Microsoft Teams環推出Teams服務。 這項功能可能早于或早于 4.0.105.0 用戶端更新

<sup>2</sup>需要 IT 系統管理員開啟Microsoft Whiteboard。 此外，如果您的會議室顯示器前方有觸控功能，則必須使用裝置系統管理員登入的 Windows 設定來校正多個觸控顯示器，才能從共用至會議Microsoft Whiteboard會議室顯示器開始使用 Teams 共同操作

### <a name="40850-0482019"></a>2019/04/8 (4.0.85.0) 

此更新仲介紹：

- 修正「提供意見回饋」功能的問題
- 準備即將升級至 Microsoft Teams 會議室 1809 Windows 10的優化

### <a name="40780-03142019"></a>2019/03/14 (4.0.78.0) 

此更新仲介紹：

- 修正影響舊版 RS2 Windows 10裝置上的「應用程式啟動Windows 10錯誤。

### <a name="40760-03042019"></a>2019/03/04 (4.0.76.0) 

此更新仲介紹：

- DTMF 鍵台Microsoft Teams P2P 會議和 PSTN 通話。 若要Microsoft Teams通話用戶端，系統管理員必須將 IsTeamsDefaultClient 設為 true
- 將遠端參與者的傳入視像釘到會議室顯示器前方的全螢幕。 使用主機上參與者名冊上的「釘釘」命令
- 大廳通知的改良功能，以及會議室前方通知的新增功能
- 當裝置上未啟用藍牙時，會議室顯示強制轉換圖示Microsoft Teams 會議室移除
- 修正會議中音量控制Teams問題

### <a name="40640-12142018"></a>2018 年 12 月 14 (4.0.64.0) 

此更新仲介紹：

- 在兩個會議室前顯示內容 (FoR) 在雙螢幕會議室系統上顯示
- 功能與會議室使用者介面的改良功能
- TLS 1.2 用戶端支援。 針對內部部署客戶，Microsoft Teams 會議室 的 TLS 1.2 啟用通訊需要 商務用 Skype Server 2015 累積更新 9 (CU9) 或 商務用 Skype Server 2019 累積更新 1 (CU1) 。

### <a name="40510-11172018"></a>2018 年 11 月 11 (4.0.51.0) 

此更新仲介紹：

- 會議室 (的雙顯示器) 會議Teams支援

### <a name="40310-10162018"></a>2018/10/16 (4.0.31.0) 

此更新仲介紹：

- 品質和可靠性修正

### <a name="40270-1012018"></a>2018 年 10 月 10 (4.0.27.0) 

此更新仲介紹：

- 準備應用程式供Microsoft Teams 會議室版本 1803 升級Windows 10程式碼變更
- 修正當地語系化 EULAs 的格式設定問題 (特別是挪威文) 避免超出 EULA OOBE 設定視窗
- 若要在舊版 Lync 會議室系統上Microsoft Teams 會議室應用程式所需的程式碼變更。 請在這裡[查看更多。](./lrs-migration.md)

### <a name="40190-8312018"></a>2018 年 8 月 8 (4.0.19.0) 

此更新仲介紹：

- 無法啟動的Cresron應用程式的 Hotfix 通常會在按下Crsron SR 裝置上的應用程式按鈕時便於使用。 Microsoft Teams 會議室 4.0.19.0 之後，需要重新開機應用程式。

### <a name="40180-08272018"></a>2018/08/27 (4.0.18.0) 

此更新仲介紹：

- 「報告問題」功能在 Teams 模式中 (相當於 「提供意見商務用 Skype」) 
- 啟用 SIP 通話從Teams商務用 Skype回到通話模式
- 使用旁白 (、放大鏡和放大鏡的協助工具) 
- 在 XML 資源配置變更已適用之後，在需要時自動重新開機應用程式
- 其他修正

### <a name="4080-07062018"></a>2018/07/06 (4.0.8.0) 

此更新仲介紹：

- 此更新可在會議室系統 *商務用 Skype Teams* 會議支援。 Teams更新後，系統預設會關閉該按鈕。 系統管理員可以在裝置Teams或透過遠端 xml 推入，在裝置設定中啟用此設定。

### <a name="311150-06182018"></a>2018/06/18 (3.1.115.0) 

此更新仲介紹：

- 修正在應用程式啟動期間在某些系統上觀察到的錯誤。

### <a name="311130-06132018"></a>2018/06/13 (3.1.113.0) 

此更新仲介紹：

- 讓 Microsoft 更靈活地管理更新Windows變更。
- 使用者體驗沒有變更。

### <a name="311120-06052018"></a>2018/06/05 (3.1.112.0) 

此更新仲介紹：

- 修正在連接到兩個會議室前顯示器和視Surface Pro裝置上所觀察到的主機回應問題
- 自動檢查以確保系統執行最新的資源配置腳本

### <a name="311040-04162018"></a>2018/04/16 (3.1.104.0) 

此更新仲介紹：

- 修正在 Windows 10 (1709) 中改善 OSK 鍵盤和螢幕小鍵盤的行為
- 準備未來作業系統更新的改良功能

### <a name="311000-03162018"></a>2018/03/16 (3.1.100.0) 

此更新仲介紹：

- 應用程式已更新以改善遙測

### <a name="31990-03142018"></a>2018/03/14 (3.1.99.0) 

此更新仲介紹：

- 修正可能發生間歇性會議加入問題的問題
- 修正已知會導致裝置「掛斷」體驗的問題

### <a name="31980-382018"></a>2018 年 3 月 3 (3.1.98.0) 

此更新仲介紹：

- 錯誤/當機修正以改善穩定性
- 支援可變大小的主機
- 外部音訊處理卸載 (媒體允許清單) 
- 可讓 IT 專業人員使用版本 1709 年 1 月更新Windows 10建立自己動手的影像的優化。

### <a name="30160-11272017"></a>2017/11/27 (3.0.16.0) 

此更新仲介紹：

- 修正「提供意見回饋」功能的問題。

### <a name="30150-1032017"></a>2017 年 10 月 3 (3.0.15.0) 

此更新仲介紹：

- 支援 [Polycom MSR 系列](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) 固定式硬體
- 支援 [Logitech Brio](https://www.logitech.com/product/brio)
- 解決當會議室沒有 (時，) 主機和會議室前顯示器無法進入睡眠模式的問題

### <a name="30120-912017"></a>2017/9/1 (3.0.12.0) 

此更新仲介紹：

- 在 2017 Surface Pro (平板電腦) 執行
- 支援Windows 10 企業版 Creator 的更新 (英文、建立 1703) 
- 支援 [Crsron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system) Dock 硬體
- Cresron (環境控制項的 OEM 支援) 

自 Microsoft Teams 會議室 版本 3.0.12.0 (更新 3) 起，不再支援 64 位版本的 Windows 10 企業版 紀念日版 (英文版本 1607) 。

### <a name="3080-842017"></a>2017 年 8 月 4 (3.0.8.0) 

此更新仲介紹：

- 解決透過參與者搜尋欄位搜尋聯合使用者時所觀察的問題。 在此修正程式之前，外部聯合使用者的搜尋結果可能無法正確解決，反而會退回不正確的結果。

### <a name="3060-772017"></a>2017 年 7 月 7 (3.0.6.0) 

此更新仲介紹：

- Dual-Screen支援 (舊版系統奇偶) 
- 主題 (內建的主題，以及設定自訂主題) 
- 提供公用建立的意見回饋的能力
- 改善會議加入可靠性的遙測
- 改良的 OMS 報告
- IT 系統管理員遠端設定裝置的能力

### <a name="2020-03152017"></a>2017/03/15 (2.0.2.0) 

此更新仲介紹：

- 應用程式內使用者選擇會議室音訊和視像 USB 裝置
- 使用 Microsoft Operations Management Suite 的整合式會議室主控台狀態報表，現在為 Azure 監視器

### <a name="release-to-market-1272016"></a>2016/ (12/7 發行) 

**功能 (功能) ：**

 **專為商務用 Skype**

- 會議中的單鍵Skype加入
- Skype針對螢幕填滿 HD 影片和 HD 寬頻音訊的會議室優化會議體驗
- 所有參與者都可以從Skype，使用他們所選擇的裝置連接到會議
- 從目錄中邀請人員，您可以立即看到他們的可用性，或透過電話通話
- 支援商務用 Skype PSTN 會議和 PSTN 通話以取代會議室中的獨立會議電話

 **轉換任何會議室**

- 專為Skype觸控式控制器和大型會議室顯示器前方優化的專用會議應用程式
- 重複使用會議室顯示器或投影機前方的現有投資
- 適用于所有類型的會議空間，從空間到大型會議室
- 已商務用 Skype音訊和視音訊裝置適用于各種會議室大小
- 內建的有線進給專案桌面共用至會議室和Skype會議

 **易於部署、易於管理**

- 當裝置偵測到會議室中的人員時，會自動喚醒顯示器的永遠啟動裝置
- 簡單部署及更新 UWP (平臺Windows應用程式) Skype應用程式
- WindowsAppLocker 將裝置鎖定至 Skype 應用程式
- 透過 Intune 和 Configuration Manager Windows 10 企業版管理 MDM (管理) 
- Enterprise等級的可靠性
- 由於熟悉使用者介面，使用者的訓練投入Skype低
- 在平板Surface Pro 4上執行

<a name="See"> </a>
## <a name="see-also"></a>另請參閱

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[準備您的環境](rooms-prep.md)

[支援Microsoft Teams 會議室分支版本](rooms-lifecycle-support.md)

[已知問題](known-issues.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)
