---
title: 規劃Microsoft Teams管理
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 規劃營運角色並指派品質支援者，以交付並維護高品質的部署。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b940ad9347e2a91a3816eb95817e59368692290
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094741"
---
# <a name="plan-my-service-management"></a>規劃我的服務管理

本文概述提供和維護高品質的部署Microsoft Teams需求。 在第一次試驗或生產部署之前，您可以在構想階段規劃服務管理和品質，協助確保部署成功。

## <a name="service-management-for-teams"></a>適用于 Teams

服務管理是一個廣泛的主題，涵蓋服務部署及啟用Microsoft Teams服務之日常操作。 Teams服務包含Microsoft 365 Office 365部署于內部部署架構的基礎結構元件，例如 (網路) 。

服務管理的概念對於大多陣列織來說，很可能不是一個新概念。 您可能已經實施與現有服務相關聯的程式與工作。 也就是說，當您今天規劃服務管理時，或許可以擴充現有功能，Microsoft Teams未來的服務管理。

服務管理包含管理端對端管理Microsoft Teams活動與程式。 服務管理的一些元件 ，Microsoft 365 或 Office 365 服務本身所組成的基礎結構元件，是 Microsoft 的責任，而客戶則須向使用者負責，以管理 Teams、網路和端點提供的各個層面。
若要全面探討客戶對服務管理的責任，Teams服務管理與支援使用者體驗品質的關鍵元件之間如何相關，請參閱服務管理與品質[規劃](./prepare-network.md)。

![品質的三個元件圖表](media/plan-my-service-management-image1.png "品質的三個元件圖表，Microsoft 365或Office 365服務、網路和端點，以及服務管理如何與這三者重迭。")

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a>操作指南簡介 

**什麼是****、神秘，****以及服務管理** 時需要回答的三項重要問題。

您可以使用操作 [指南](./1-drive-value-operate-my-service.md) 來協助解決這三個問題。 本指南提供每日、每週、每月和需要執行的活動清單。 這些活動和工作對於維護高品質的部署Teams至關重要。 判斷誰負責執行服務管理中的特定活動，是規劃的一個至關重要環節，您必須在構想階段初期進行，以確保部署成功。 當您找出工作與活動之後，必須瞭解這些工作與活動，後面接著您指派給他們的群組或個人。 操作指南提供如何執行每項工作的知識與指引，以及/或參照外部內容。

## <a name="plan-for-operational-role-mapping"></a>規劃操作角色的映射

提早規劃服務管理是一個重要的里程碑，因為當第一個試驗使用者啟用時，操作階段即會開始。 專案小組必須審查並同意所需的工作與活動，找出負責每項作業任務的團隊，然後從每個小組取得承諾和簽收。

登出完成後，負責的小組必須開始執行這些角色和職責。 這可能包括訓練與準備、更新人員配置模式，或確保外部合作夥伴準備好提供。

在構想階段初期，規劃營運角色可讓所有團隊在試驗期間開始其營運工作，並加快作業，並確保部署開始後一切就緒。

操作指南提供對應到一般角色的常見工作清單，在大多數情況下應該有效。 您必須自訂這些職責，為貴組織工作。

>[!TIP]
>以下是一個範本範例，用於記錄您為支援此專案所執行之操作角色映射作業的結果。


|操作角色 |描述 |團隊 |連絡人詳細資料 |
|---------|---------|---------|---------|
|服務擁有者|服務擁有者、營業單位介面、策略|Tba|Tba|
|音訊會議作業|每日作業、使用者與裝置帳戶移動/新增/變更、監控|Tba| Tba| 
|租使用者系統管理員|變更租使用者範圍的設定，啟用新功能|Tba|Tba|
|服務台|使用者取得支援的介面|Tba|Tba|
|網路營運|執行 LAN、WAN、Wi-Fi 和網際網路存取|Tba|Tba|
|用戶端&端點小組|管理桌面部署|Tba|Tba|
|身分識別作業|管理 Active Directory (Active Directory、Active Directory Federation Services、Azure AD) |Tba|Tba|
|採用/變更管理|管理解決方案的感知、訓練和採用|Tba|Tba|
|Exchange操作|管理Exchange環境|Tba|Tba|
|電話營運|管理 SBC 和電話號碼|Tba|Tba|

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a>品質冠軍角色

群組或個人必須負責所有組織的品質。
這是服務管理中最重要的角色。 品質保護者是指派給對使用者體驗充滿熱忱之人員或群組的客戶角色。 這個角色需要識別環境趨勢的技能，以及與其他團隊合作推動補救的贊助。
品質優等獎得主的最佳人選通常是客戶服務擁有者，根據組織的規模和複雜度，他們可能是任何對使用者體驗充滿熱忱的人或群組。

品質支援者利用現有工具和檔化程式 ，例如通話品質儀表板 (CQD) 和品質體驗檢閱指南，以監控使用者體驗、識別品質趨勢，並視需要推動補救。 品質保護員會與各個小組合作，推動補救動作、向指導委員會報告其進度和開啟問題。

與角色相關聯的工作和活動會記錄在作業指南中。 此角色應于構想階段早期指派。 將品質維護者角色運作的關鍵步驟，是取得角色所需的知識，並確保具備完成任務的先決條件。 此角色的一項重要工作就是執行一般品質體驗檢閱。

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a>品質經驗檢閱指南簡介

品質經驗檢閱指南有一組活動，可評估對改善使用者體驗影響最大的重要領域，並提供補救指南，如下圖所示。

![品質經驗檢閱期間要檢查的重要區域圖例](media/plan-my-service-management-image2.png "品質體驗檢閱期間要檢查的重要區域：音訊、可靠性及使用者問卷結果。")

您可以持續評估及補救本檔所述區域，以減少其潛在影響使用者體驗。 部署中遇到的大多數使用者體驗問題可以分成下列類別：

-   不完整的防火牆或 Proxy 組

-   低Wi-Fi覆蓋

-   頻寬不足

-   Vpn

-   使用非初始化或內建的音訊裝置

-   有問題的子網或網路裝置

品質經驗檢閱指南所提供的指引著重于使用通話品質儀表板 (CQD) Online 做為報告及調查所述每個領域的主要工具，並著重于音訊，以最大化採用和影響。 對網路進行的任何優化以改善音訊體驗，也會直接轉換成改善視像和桌面共用。

我們強烈建議您及早提名品質優等獎得主。 獲得提名後，他們應開始熟悉品質經驗檢閱指南 [中的內容](./quality-of-experience-review-guide.md)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定誰負責貴組織的雲端語音作業。</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>下載服務管理規劃完整指南。</li><li>下載品質體驗檢閱指南。</li><li>完整閱覽作業指南。</li><li>提供所有指南給每個作業小組成員，以審查並熟悉作業需求。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->