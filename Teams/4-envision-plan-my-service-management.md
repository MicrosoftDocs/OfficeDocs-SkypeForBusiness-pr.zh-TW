---
title: 規劃 Microsoft 團隊服務管理
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 規劃運營角色並指派品質擁護者來提供和維護高品質的部署。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bab0026b14514114f9c6e975046ee561dade6f40
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516759"
---
# <a name="plan-my-service-management"></a>規劃我的服務管理

本文概述傳送和維護高品質 Microsoft 團隊部署所需的需求。 您可以在進行第一次試驗或生產部署前，在構想階段規劃服務管理和品質，以協助確保順利進行部署。

## <a name="service-management-for-teams"></a>團隊的服務管理

服務管理是一個廣泛的主題，涵蓋在部署並為使用者啟用 Microsoft 團隊服務之後的日常作業。 [團隊服務] 包含 Microsoft Office 365 和部署于內部部署的基礎結構元件（例如 [網路]）。

服務管理的概念很可能不是大多陣列織的新概念。 您可能已經實現與現有服務相關聯的進程和工作。 如此一來，您可能會在規劃服務管理時補充所需的內容，以備日後支援 Microsoft 團隊。

服務管理包括管理 Microsoft 團隊端到端的所有活動與程式。 服務管理的部分元件（由 Office 365 服務本身所組成的基礎結構元件）是 Microsoft 的責任，而客戶對其使用者負責管理團隊、網路和的各個方面。其提供的端點。
如需團隊服務管理的客戶責任以及其與 underpin 使用者體驗品質的關鍵元件的完整討論，請參閱[規劃服務管理和品質](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide)。

三個品質元件（即 Office 365 服務、網路及端點）的![三個品質元件]圖表，(media/plan-my-service-management-image1.png "以及服務管理如何與這三個元件重迭。")

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a>操作指南簡介 

**何謂**、**誰**，以及**如何**在服務管理方面需要解答的三個重要問題。

您可以使用 [[操作指南](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)] 協助您解決這三個問題。 本指南提供每日、每週、每月以及視需要執行的活動清單。 這些活動和工作對於維護高品質的小組部署而言是至關重要的。 決定要在服務管理中執行特定活動的人員，是規劃的一個重要層面，您需要儘早在 Envision 階段進行，以確保順利進行部署。 在您發現任務和活動之後，必須先瞭解這些工作和活動，然後再按您指派給他們的群組或人員。 本操作指南針對如何執行每項工作以及/或外部內容的參考，提供相關知識與指導方針。

## <a name="plan-for-operational-role-mapping"></a>規劃操作角色對應

儘早規劃服務管理是一個重要的里程碑，因為「操作階段」是在第一個試驗使用者啟用時開始。 專案小組必須審查並同意所需的工作與活動，找出負責每個作業任務的小組，然後從各個小組取得承諾並登出。

登出完成後，負責的小組必須開始 operationalizing 這些角色和職責。 這可能包括訓練與準備、更新人力資源模型，或確保外部合作夥伴已準備好交付。

在 Envision 階段的初期對應運營角色，可讓所有團隊在試驗和加速作業期間開始其運作工作，並確保部署開始之後一切都已準備好。

本操作指南提供對應至一般角色的一般工作清單，這些工作應該在大多數情況下都有效。 您必須自訂這些職責，才能為您的組織作業。

>[!TIP]
>下列是一個範本範例，可將您執行以支援此專案的操作角色對應練習的結果進行記錄。


|操作角色 |說明 |團隊 |連絡人詳細資料 |
|---------|---------|---------|---------|
|服務擁有者|服務擁有者、公司分部介面、戰略|TBA|TBA|
|音訊會議作業|每日作業、使用者和裝置帳戶移動/新增/變更、監控|TBA| TBA| 
|租使用者管理員|變更整個租使用者的設定、啟用新功能|TBA|TBA|
|技術支援中心|使用者取得支援的介面|TBA|TBA|
|網路作業|執行局域網、WAN、Wi-fi 和網際網路存取|TBA|TBA|
|用戶端 & 端點小組|管理桌面部署|TBA|TBA|
|身分識別作業|管理身分識別結構（Active Directory、Active Directory Federation Services、Azure AD）|TBA|TBA|
|採納/變更管理|管理解決方案的意識、訓練及採納|TBA|TBA|
|Exchange 操作|管理 Exchange 環境|TBA|TBA|
|電話作業|管理 SBC 和電話號碼|TBA|TBA|

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a>品質擁護者角色

群組或個人需要負責所有組織中的品質。
這是服務管理中最重要的角色。 品質擁護者是指派給人員或群組的客戶角色，他們會熱情他們的使用者經驗。 這個角色需要技能來識別環境中的趨勢，以及與其他團隊合作來促進修正的贊助。
品質擁護者的最佳候選方案通常是客戶服務擁有者，他們可以根據組織的大小與複雜性而定，誰是熱情使用者體驗的人員或群組。

[品質擁護者] 利用現有的工具與已記錄的程式，例如 [通話品質儀表板] （CQD）和 [品質體驗檢查指南]，以監控使用者體驗、識別品質趨勢，以及在必要時進行磁片磁碟機修正。 品質擁護者與各個小組合作，以促進修正動作，向指導委員會報告其進度和開啟的問題。

[作業指南] 中記錄了與角色相關聯的工作和活動。 這個角色應該在構想階段中儘早指派。 Operationalizing 品質擁護者角色的主要步驟是取得該角色所需的知識，並確保準備好要提供該工作所需的預備作業。 此角色的主要工作是執行定期品質體驗審查。

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a>[品質體驗回顧指南] 簡介

[品質體驗檢查指南] 中有一組活動，可針對改善使用者體驗的主要區域評估並提供修正指導方針，如下圖所示。

[![品質體驗] 中要檢查的主要區域圖例查看](media/plan-my-service-management-image2.png "品質體驗檢查期間要檢查的重要區域：音訊、可靠性及使用者問卷調查結果。")

透過不斷評估與修正本檔中所述的區域，您可以減少對使用者經驗造成負面影響的可能性。 在部署中遇到的大多數使用者體驗問題，都可以分為下列類別：

-   防火牆或 proxy 配置不完整

-   低 wi-fi 覆蓋範圍

-   頻寬不足

-   點對點

-   使用未優化或內建的音訊裝置

-   有問題的子網或網路裝置

[品質體驗回顧指南] 中所提供的指導方針主要是使用 [通話品質儀表板（CQD）] 作為主要工具來報告和調查所述的每個區域，並將焦點放在音訊上以最大化採納與影響。 針對網路所做的任何優化，以改善音訊體驗，也會直接翻譯成影片和桌面共用的改良功能。

我們強烈建議您提前提名品質擁護者。 命名之後，他們應該開始熟悉[品質體驗回顧指南](https://aka.ms/qerguide)中的內容。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定誰負責貴組織中的雲端語音作業。</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>下載 [服務管理的規劃] 完整指南。</li><li>下載 [品質體驗回顧指南]。</li><li>完整回顧 [操作指南]。</li><li>將所有指南提供給每個作業小組成員，以進行審查並熟悉作業需求。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->