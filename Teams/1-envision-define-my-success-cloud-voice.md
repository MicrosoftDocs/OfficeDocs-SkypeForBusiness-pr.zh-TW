---
title: 音訊會議、通話方案或直接路由
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 定義音訊會議部署的成功、電話系統通話方案，或電話系統直接路由。
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e669e0454f65ef4d3d5ecc0b4832b33201d2703
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011757"
---
# <a name="define-my-success"></a>定義我的成功

本文概觀了定義音訊會議部署成功、使用電話系統方案，或為貴組織電話系統直接路由的需求。 您可以正確定義成功的外觀，以在部署進行時測量結果，並確認您取得的結果是想要的結果。

<!--ENDOFSECTION-->

音訊 **會議** 可透過使用傳統有線電話、私人分支交換 (PBX) 或行動電話撥入，讓會議參與者透過公用交換電話網路絡 (PSTN) 加入任何會議 (臨時或排定的) ，為組織提供額外的進入點。 如果召集人或參與者不在電腦前面，或是資料連線無法使用或太不可靠，無法支援語音通訊時 ，例如行動資料覆蓋不穩定的遠端區域，或以有限頻寬連接到免費的公用 Wi-Fi 服務，或是會議參與者偏好使用電話端點撥入會議，那麼這項功能會很有用。

**電話系統通話方案 (「通話方案」)** 讓使用者從電腦和行動裝置撥打商務相關電話，讓組織能夠現代化工作場所。 工作場所現代化可以是任何案例的一部分，例如以活動為基礎的工作執行工作、重大辦公室移動、辦公室調整重新規劃、淘汰舊版 PBX 解決方案、PSTN 服務提供者合約的簽訂等等。 Microsoft 使用通話方案可協助 PSTN 的連接。

**電話系統直接路由 (「直接路由」)** 為組織提供上述通話方案相同的權益，但協力廠商提供者而非 Microsoft 可協助 PSTN 連接。 這可讓部署在未提供通話方案的國家/地區，或需要維護現有 PSTN 服務提供者合約或需要與特定內部部署系統的互通性的部署。 考慮直接路由的另外一個案例是電話系統互通性。 當使用者在通話中轉換至通話Teams，部分使用者可能仍然使用舊版 PBX。 直接路由可讓兩個使用案例並存。 舊版系統上的使用者與使用者之間的Teams流量會維持在組織中。

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>定義音訊會議、通話方案或直接路由的商務使用案例

首先，核心專案關係人必須定義支援音訊會議、通話方案或直接路由的商務使用案例。

商務使用案例旨在定義及記錄預期及可測量的商業結果，並包含下列專案：

-   目前商務程式的描述

-   現有商務程式的挑戰

-   科技如何協助克服這些挑戰

-   如果挑戰已解決，預期且可衡量的商業結果

> [!TIP]
> 以下是音訊會議已完成商務使用案例的範例：
> 
> |         |
> |---------|
> |**目前商務程式的描述**<br>Contoso 目前仰賴由現有當地電話提供者提供的 PSTN 會議服務，其費用以會議分鐘數收費，適用于內部會議和涉及外部各方的會議。|
> |**現有商務程式的挑戰**<br>Contoso 每年約花費 100 萬美元，用於目前的 PSTN 會議服務，其中 75% 的成本是內部會議產生的。 使用傳統電話端點加入 PSTN 會議服務所主持的會議，與組織採用 Teams 做為現代化通訊和共同合作平臺的計畫並不一致。|
> |**技術如何克服這些難題**<br>隨著採用 Microsoft Teams 作為現代化通訊和共同合作平臺，內部使用者主要預期會使用配備優化耳機和會議室裝置之電腦加入會議。 音訊會議服務可支援外部參與者，或支援內部參與者使用 PC 音訊不優惠的情況。|
> |**預期、可測量的商務成果**<br>移轉Teams現代化通訊和共同合作平臺，結合音訊會議服務，將大幅降低提供 PSTN 會議服務的成本。|

<br>

> [!TIP]
> 以下是通話方案已完成商務使用案例的範例：
> 
> |         |
> |---------|
> |**目前商務程式的描述**<br>Contoso 辦公室工作區的標準配置包含適用于每個辦公桌的桌面電話。 每個員工都獲得一個直接撥入號碼 (DID) 電話號碼。 桌面電話會連接到 PBX 系統，並透過會話初始通訊協定與 SIP (網) PSTN。 員工只能在指派的桌面電話撥打和接聽電話。|
> |**現有商務程式的挑戰**<br>桌面電話的使用狀況分析顯示，只有 10% 的桌面電話是主動使用，其餘的電話則配置為將電話轉往行動電話，或同時撥打到行動電話。 維護現有的 PBX 系統和相關桌面電話占 Contoso 每月電話語音成本的 20%。|
> |**技術如何克服這些難題**<br>通話方案會利用原生應用程式，讓使用者的個人電腦在資料網路上接聽Microsoft Teams電話。 這移除了推出及維護桌面電話的需要，並開啟瞭解除現有 PBX 系統解除授權的機會，因為電話語音可以透過雲端透過網路傳遞，而與傳統電話系統沒有相依性。|
> |**預期、可測量的商務成果**<br>移除維護需求並解除舊版 PBX 和桌面電話的解除授權，將每月的電話語音支出減少 20%。 通話方案會簡化辦公室工作區，讓 Contoso 以最低的預付電話成本建立新辦公室，以擴充其營運。|

<br>

> [!TIP]
> 以下是直接路由的已完成商務使用案例範例：
> 
> |         |
> |---------|
> |**目前商務程式的描述**<br>Contoso 辦公室工作區的標準配置包含適用于每個辦公桌的桌面電話。 每個員工都獲得一個直接撥入號碼 (DID) 電話號碼。 桌面電話會連接到 PBX 系統，並透過會話初始通訊協定與 SIP (網) PSTN。 員工只能在指派的桌面電話撥打和接聽電話。|
> |**現有商務程式的挑戰**<br>桌面電話的使用狀況分析顯示，只有 10% 的桌面電話是主動使用，其餘的電話則配置為將電話轉往行動電話，或同時撥打到行動電話。 維護現有的 PBX 系統和相關桌面電話占 Contoso 每月電話語音成本的 20%。|
> |**技術如何克服這些難題**<br>SIP 主幹提供者合約最近已簽署，將會執行三年。 直接路由可讓 SIP 主幹提供者提供 PSTN 連接，並允許使用者的個人電腦利用原生應用程式，在資料網路上接收Microsoft Teams電話。 這移除了推出及維護桌面電話的需要，並開啟瞭解除現有 PBX 系統解除授權的機會，同時維持有限的內部部署會話邊界控制器 (SBC) 佔用。|
> |**預期、可測量的商務成果**<br>移除維護需求並解除舊版 PBX 和桌面電話的解除授權，將每月的電話語音支出減少 20%。 直接路由可簡化辦公室工作區，讓 Contoso 以最低的預付電話成本建立新辦公室，以擴充其營運。|

除了定義業務使用案例之外，若要設定專案界限，您也應該致力於推動清楚：

-   **組織範圍：** 音訊會議、通話方案或直接路由的實現可能包含整個組織或僅包含特定的業務單位。

-   **Project時程表：** 專案將會執行的特定時程表。

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |決策點|<ul><li>您可以在貴組織中識別音訊會議的所有商務使用案例是什麼？</li><li>您可以識別組織中通話方案的所有商務使用案例是什麼？</li><li>您可以識別組織中直接路由的所有商務使用案例是什麼？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|後續步驟|<ul><li>記錄貴組織音訊會議的所有商務使用案例。</li><li>記錄貴組織通話方案的所有商務使用案例。</li><li>記錄貴組織直接路由的所有商務使用案例。</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>識別重要的專案關係人

上一個步驟中定義的商務使用案例包含音訊會議、通話方案或直接路由實現的組織範圍。 基於此，您可以完成完整的專案關係人矩陣，以包含要參與專案的合適人員。

> [!TIP]
> 以下是專案關係人矩陣範本範例，您可以使用此範本來記錄專案專案關係人：
> 
> |角色  |描述  |名稱、連絡人資訊、位置  |
> |---------|---------|---------|
> |Project執行贊助人|<ul><li>針對專案與交付專案目標，採取終極授權與責任。</li><li>協助解決由潛在客戶Project的問題。</li><li>贊助公司內部有關專案目標的通訊。</li><li>做出重要的策略決策。</li><li>確保可用所需的資源和預算。</li><li>在 QBRs 中 (季業務) 。</li><li>推動認知活動活動的購買和支援。</li><li>擔任計畫Project的贊助商。</li></ul>|TBA|
> |Project導致|<ul><li>管理並帶領專案小組。</li><li>協調參與專案的合作夥伴和工作組。</li><li>負責建立及管理專案計劃，以滿足每季的重要結果。</li><li>解決跨功能問題。</li><li>提供定期更新給專案贊助者。</li><li>將採用層面納入全能專案計劃。</li><li>引導每月商務與營運評論 (MBRs) 參與 QBRs。</li></ul>|TBA|
> |共同合作主管/架構|<ul><li>執行由公司主管定義的共同合作策略。</li><li>分析並選擇符合公司商業目標的共同合作產品。</li><li>共同作業產品的設計作業。</li><li>定義作業和支援模型。</li><li>參與每月和每季商務評論。</li></ul>|TBA|
> |顧問|<ul><li>負責組組服務</li><li>參與整體解決方案架構。</li></ul>|TBA|
> |專案經理|<ul><li>開發及維護專案計劃。</li><li>根據專案計劃和預算管理專案交付專案。</li><li>記錄及管理專案問題，包括升級。</li><li>進行每週的備份通話。</li><li>與專案執行贊助者進行聯絡並提供更新。</li><li>與架構設計師共同定義變更管理方法與通訊計畫。</li></ul>|TBA|
> |變更管理/採用專家|<ul><li>在探索階段提供採用與訓練程式的意見。</li><li>參與採用策略研討會。</li><li>制定採用策略並負起責任。</li><li>開發並執行通訊計畫。</li><li>提供訓練給使用者。</li><li>收集意見意見並進行調查。</li></ul>|TBA|
> |網路潛在客戶|<ul><li>在探索階段提供網路設計的意見。</li><li>在構想階段研討會期間參與規劃。</li><li>在專案執行期間協調網路小組的工作。</li></ul>|TBA|
> |安全性潛在客戶|<ul><li>在探索階段提供安全性設計與程式的意見。</li><li>在構想階段研討會期間參與規劃。</li><li>在專案執行期間協調安全小組的工作。</li></ul>|TBA|
> |電話潛在客戶|<ul><li>在探索階段提供電話設計的意見。</li><li>在構想階段研討會期間參與規劃。</li><li>在專案執行期間協調電話小組的工作。</li></ul>|TBA|
> |桌面潛在客戶|<ul><li>在探索階段向用戶端和更新程式提供輸入。</li><li>在構想研討會期間參與規劃。</li><li>在專案執行期間協調桌面小組的工作。</li></ul>|TBA|
> |支援/服務台潛在客戶|<ul><li>在探索階段提供投入，以納入營運和支援模型。</li><li>在構想階段研討會期間參與規劃。</li><li>參與支援模型規劃。</li><li>在專案執行期間協調支援小組和資源的工作。</li></ul>|TBA|
> |業務單位代表|<ul><li>參與以使用者為基礎的採用指南和教材。</li><li>參與及審查商務使用案例。</li></ul>|TBA|
> |部署潛在客戶|<ul><li>確保符合部署先決條件。</li><li>使用資源參與板載階段活動。</li><li>參與會議以審查及準備部署狀態報表。</li></ul>|TBA|
> |IT 系統管理員|<ul><li>協助測試規劃及執行。 此角色適用于 IT 專業人員。</li></ul>|TBA|
> |服務擁有者|<ul><li>負責音訊會議、通話方案或直接路由服務的執行。</li><li>擁有音訊會議、通話方案或直接路由服務。</li></ul>|TBA|
> |品質優勝者|<ul><li>提升品質、可靠性和使用者意見。</li><li>找出品質趨勢，並推動各小組進行補救。</li><li>透過指導委員會向領導階層報告。</li><li>透過評分我的通話和 Net 啟動者分數，報告品質、可靠性及使用者情緒。</li></ul>|TBA|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|決策點|<ul><li>哪些人會為貴組織填入每個重要的專案關係人角色？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|後續步驟|<ul><li>記錄所有重要的專案關係人，並將角色的責任和期望傳達給每個指派的個人。</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>定義 OKRs、KSIs 和風險

集合專案專案關係人之後，您可以將商務使用案例、組織範圍和專案時程表轉換成目標與重要結果 (OKRs) ，而專案成功的度量單位可定義為關鍵成功指示器清單 (KSIs) 。

專案專案關係人全面參與定義 OKRs 和 KSIs 對於協助確保他們擁有權感，以及讓這些成功量度與組織商務需求保持一致至關重要。

OKRs 包含您于專案開始時設定的目標，而且您每季定義可測量的重要結果。 您每月會檢查重要結果，以追蹤整體專案的狀態，並依據進度調整每季計畫。

> [!TIP]
> 以下可參照與音訊會議實現相關的 OKRs 範例：
> <br>
> 
> **願景：最大化 Microsoft 365 或 Office 365 投資以提高生產力**
> 
> |目標  |重要結果  |執行  |
> |---------|---------|---------|
> |在 2018 會計年度結束時在 Teams 中部署音訊會議|FY18Q1：在 Teams 全域部署音訊會議|構想<ul><li>建立成功計畫</li><li>建立詳細的技術執行計畫</li></ul><p>快速上手<ul><li>執行成功計畫</li><li>執行技術執行計畫</li></ul>|
> |在 2018 會計年度中停用舊版 PSTN 會議服務|FY18Q2：在全球停用舊版 PSTN 會議服務|發揮價值<ul><li>提升使用者參與度並推動採用</li><li>管理和準備變更</li><li>測量、分享成功並測試</li>|

<br>

> [!TIP]
> 以下可參照與通話方案實現相關的 OKRs 範例：
> <br>
> 
> **願景：最大化投資或Microsoft 365 Office 365生產力**
> 
> |目標  |重要結果  |執行  |
> |---------|---------|---------|
> |在 2018 會計年度結束時在歐洲分公司部署通話方案|FY18Q3：部署倫敦辦公室的通話方案|構想<ul><li>建立成功計畫</li><li>建立詳細的技術執行計畫</li></ul><p>快速上手<ul><li>執行成功計畫</li><li>執行技術執行計畫</li></ul>|
> |在 2018 會計年度結束前停用倫敦辦公室的舊版 PBX|FY18Q4：停用倫敦辦公室的舊版 PBX|發揮價值<ul><li>提升使用者參與度並推動採用</li><li>管理和準備變更</li><li>測量、分享成功並測試</li>|
> 
> [!TIP]
> 以下可參照與直接路由實現相關的 OKRs 範例：
> <br>
> 
> **願景：最大化投資或Microsoft 365 Office 365生產力**
> 
> |目標  |重要結果  |執行  |
> |---------|---------|---------|
> |在 2018 會計年度結束時，在加拿大分公司部署直接路由|FY18Q3：在多倫多辦公室部署直接路由|構想<ul><li>建立成功計畫</li><li>建立詳細的技術執行計畫</li></ul><p>快速上手<ul><li>執行成功計畫</li><li>執行技術執行計畫</li></ul>|
> |在 2018 會計年度結束前停用在多倫多辦公室的舊 PBX|FY18Q4：在多倫多辦公室停用舊版 PBX|發揮價值<ul><li>提升使用者參與度並推動採用</li><li>管理和準備變更</li><li>測量、分享成功並測試</li>|

<br>

KSIs 會測量關鍵結果的品質和成功，並詳述良好和/或不佳的結果 (可補充 OKRs (達到或未) 二進位性質。

定義 KSIs 時，建議您在 SMART 準則中，使用「特定、可測量、可指派、實際、 (時間) 準則：

-   特定：針對特定領域進行改進

-   可測量：量化或至少建議進度的指示器

-   可指派：指定誰將執行此工作

-   實事求是：說明在提供可用資源時，可以實際取得哪些結果

-   時間相關：指定何時可以取得結果

> [!TIP]
> 以下是與此專案相關的 KSI 範例：
> 
> |類型  |KSI 問題&準則  |測量方式  |成功準則  |測量  |負責  |
> |---------|---------|---------|---------|---------|---------|
> |使用/採用|通話品質等於或高於先前的解決方案|調查|80% 的使用者同意或強烈同意|啟用後及每季|資訊技術小組|
> |使用/採用|Microsoft Teams讓通訊程式更容易|調查|80% 的使用者同意或強烈同意|啟用後及每季|變更管理團隊|
> |使用/採用|使用者主動使用解決方案|Microsoft 365、通話品質儀表板|80% 的使用者是每日使用中的使用者|日常|變更管理團隊|
> |使用量/品質|通話/會議不佳的百分比應該最小|通話品質儀表板|<每月 5% 的通話品質不佳|日常|資訊技術小組|
> |使用方式/支援|我知道如何取得技術支援|調查|90% 的使用者同意或強烈同意|啟用後及每季|變更管理團隊|
> |使用方式/支援|我對於技術支援的品質感到滿意|調查|80% 的使用者同意或強烈同意|每起事件之後|資訊技術小組|
> |金融|減少舊版會議分鐘數|財務系統|符合已定義的ROI|根據ROI|變更管理團隊|

您需要將商務風險識別為本練習的一部分，並針對每個已識別的風險定義緩解計畫。 這項資訊可以捕獲到風險註冊中。

> [!TIP]
> 您的風險登記簿可以記錄為下列範例：
> 
> |風險  |可能性  |影響  |整體  |緩解計畫  |
> |---------|---------|---------|---------|---------|
> |即將合併最多 1，000 人|高|高|高|<ul><li>對於合併的公司，請建立個別的 OKR，以適用于其自己的專案階段， (構想、板載、推動價值) </li><li>請勿在現有的 OKRs 中納入這些 OKRs</li></ul>|
> |電話號碼埠將會延遲專案完成|高|高|高|<ul><li>事先準備支援電話號碼轉寄的所有 (客戶服務記錄、帳單詳細資料、授權書) </li><li>調整專案時程表，以配合電話號碼轉場執行的交付時間</li><li>向外部參與者傳達使用新電話撥入式會議號碼的方式</li><li>使用臨時電話號碼與本機號碼操作</li></ul>|
> |規劃的網路重新設計|高|中型|中型|<ul><li>在將網路Teams現代化通訊和共同合作平臺之前，針對專案範圍內的網站進行網路就緒性評定</li></ul>|
> |SBC 組組|高|高|高|<ul><li>在將 Teams取代現有 PBX 之前，請確認您可以符合所有 SBC 組組需求</li><li>確認 SBC 支援資源具有設定 SBC 直接路由的適當技能集</li></ul>|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|決策點|<ul><li>貴組織&#39;OKRs 和 KSIs？</li><li>您發現哪些風險與貴組織的音訊會議執行相關？ 針對已識別的風險，哪些是減輕風險的計畫？</li><li>您發現哪些風險與貴組織的通話方案執行相關？ 針對已識別的風險，哪些是減輕風險的計畫？</li><li>您發現哪些風險與組織中直接路由的執行工作相關？ 針對已識別的風險，哪些是減輕風險的計畫？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|後續步驟|<ul><li>記錄 OKRs 和 KSIs，並建立風險註冊機構。</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>建立指導委員會

指導委員會是由重要專案關係人與專案領導者所管理，他們彙集在一起，以引導專案或計畫取得已定義之業務成果。 指導委員會不直接負責專案的交付方式，而是專案給企業提供的專案。 

每個專案都需要一致願景和章程。 若要從專案取得您想要的結果，必須清楚定義願景，而且必須監控及維護該願景。 這會成為指導委員會的責任：推動決策、提供意見、提供策略性監督、為組織宣傳專案計劃，並在必要時移除封鎖者。

貴組織應該對組成指導委員會進行重大思考。 委員會必須確保專案達到您為推動整個組織進行變更所定義的商業目標，定期開會討論專案的目前脈動，並協助解除封鎖過程中遇到的任何障礙。

委員會應定義其章程，以納入一些關鍵目標：

-   在專案小組與主管贊助者或主管領導之間保持一致。

-   向主管贊助者或主管領導提供專案狀態的深入資訊。

-   允許執行贊助者或主管領導小組為專案提供方向和意見，並調整專案計劃、目標關鍵結果 (OKRs) 及其他專案活動，確保專案符合整體的業務目標。

指導委員會會在整個專案生命週期中週期性開會，以確保組織領導與專案小組之間保持一致。 此重要會議可確保專案的方向獲得領導階層的完全支援，並將領導階層提供的任何意見回饋納入專案中，以推動成功。 委員會使用這些會議來深入瞭解專案狀態，並：

-   同意與業務案例一致的商務結果，並確保專案能夠推動這些成果的傳遞。

-   檢查並核准專案是否正確且符合商務案例。

-   審查並驗證對商務案例進行變更，可能會影響任何已定義的結果。

-   針對專案交付專案的優先順序做出策略決策，並核准臨時交付專案。

-   找出、管理及減輕需要委員會額外影響之差距、風險及問題。

-   針對需要升級、優先處理及解決專案關係人業務單位之間任何衝突的問題，向執行贊助者或主管領導小組收集支援。 

-   在適用時，向主管領導階層、變更顧問委員會或其他企業與 IT 關係人提供正式的回饋和建議。

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|決策點|<ul><li>決定貴組織是否需要一個指導委員會。</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|後續步驟|<ul><li>識別指導委員會的成員。</li><li>排程指導委員會會議。</li><li>準備引導委員會會議。</li><li>召開指導委員會會議。</li><li>根據指導委員會會議的意見採取行動。</li></ul>|

有關如何運作適當指導委員會的其他詳細指引，請見指導 [委員會指南](envision-steering-committee-complete-guide.md)。

<!--ENDOFSECTION-->
