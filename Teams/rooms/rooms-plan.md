---
title: 規劃 Microsoft Teams 會議室
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 本文說明部署 Microsoft 團隊聊天室的下一代 Skype 室系統的相關規劃考慮。
ms.openlocfilehash: ccc24aea1a45d2aa75c3b1a5de668b520483c2bd
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662468"
---
# <a name="plan-microsoft-teams-rooms"></a>規劃 Microsoft 團隊聊天室

本文將提供一種端對端的做法來規劃、交付及操作 Microsoft 團隊聊天室，成為您的整體會議和會議室戰略的一部分。

您可以在以下所示的規劃資訊中，涵蓋所需使用的建議方法和主要決定，以及支援技術資訊的連結。 我們建議您複習 [規劃]、[部署] 及 [管理] 區段，即使您已經完全部署了也一樣。

## <a name="overview-of-microsoft-teams-rooms"></a>Microsoft 團隊聊天室概覽

Microsoft 團隊聊天室提供完整的會議體驗，讓您可以在各種規模的會議（從小型 huddle 區域到大型會議室）中，將 HD 影片、音訊及內容共用帶入所有大小的會議。

![在會議室牆上安裝的主控台、麥克風及大型螢幕會說明 Microsoft [小組聊天室] 設定範例的元素。](../media/room-systems-image1.png "在會議室牆上安裝的主控台、麥克風及大型螢幕會說明 Microsoft [小組聊天室] 設定範例的元素。")

[Microsoft 團隊聊天室](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 說明是一個不錯的資源，可讓您深入瞭解 Microsoft 團隊聊天室，以及如何在您的部署中加入價值。 此外，我們也建議您觀看此 [概述影片](https://youtu.be/tNey5KZVCl0)。 

## <a name="microsoft-teams-rooms-components"></a>Microsoft 團隊聊天室元件

Microsoft 團隊聊天室包含下列主要元件，可提供良好的使用者體驗：

- 觸控式螢幕控制項面板
- 出
- Microsoft 團隊聊天室應用程式
- 固定/擴展器
- 週邊裝置 (相機、麥克風、喇叭) 
- 外部畫面 (最多兩個) 
- HDMI 輸入

您可以按照 [本文所述的需求](requirements.md)，將這些元件作為預先安裝的產品群組來購買。

除了 Surface Pro/dock 組合之外，您也可以使用觸控式螢幕控制台、計算、停靠及主要週邊設備裝置來購買 Microsoft 團隊會議室。 

一般來說，套件與整合的單元包含預先安裝的軟體，而如果您是為 Surface Pro 系統單獨購買支援的元件，您必須安裝軟體。 如需相關指示，請參閱 [這篇文章，瞭解如何在裝置上安裝軟體](rooms-scale.md)。 

您可以使用 Microsoft 團隊、商務用 Skype Online 或商務用 Skype 混合式或內部部署的部署來部署 Microsoft 團隊聊天室。  請參閱 [小組會議室授權更新](rooms-licensing.md) ，取得所需授權的相關資訊。

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您是否要在組織中部署 Microsoft 團隊會議室？ </li><li>您要如何將您的 Microsoft 團隊房間系統（已捆綁）、個別元件或整合單元購買？</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟 | <ul><li>找出將在整個部署中承擔主要活動的人員。</li><li>請查看您已 (的會議室，並規劃) ，瞭解您要部署 Microsoft 團隊聊天室的位置，以及適合會議室大小的週邊裝置。</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>找出將在整個部署中承擔重要活動的人員

使用下面所示的方法引導您完成部署，並視貴組織的需求自訂本文所提供的範例輸出。

請先瞭解您所擁有的會議室，以及對您未來的最佳作用，然後透過選取並 procuring 您所需的裝置、管理您的網站、設定及部署您的服務、管理變更與使用者採納，以及開發作業與維護程式。

![請先瞭解您擁有的功能，以及構想最適合您的功能，然後在選取並 procuring 您所需的裝置、管理變更與使用者採納，以及開發作業和維護程式。](../media/room-systems-image2.png "請先瞭解您擁有的功能，以及構想最適合您的功能，然後在選取並 procuring 您所需的裝置、管理變更與使用者採納，以及開發作業和維護程式。")

您可能需要在多個小組中協調這些活動。 我們會為您要涵蓋的主要活動提供一個高層視圖，而且也會針對通常參與部署和管理會議室系統的小組提出建議，以協助您決定需要使用的人員。

| 工作                       | 誰可能會執行任務           | 指派給 | 此內容的連結 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 庫存會議室            | 設施/AV 小組/IT 專案小組 |             | [會議室庫存與功能規劃](#room-inventory-and-capability-planning)        |
| 規劃功能          | IT 專案小組                        |             | [會議室庫存與功能規劃](#room-inventory-and-capability-planning)                       |
| 裝置選取           | IT 專案小組/AV 小組              |             | [裝置選取](#device-selection)                      |
| 購買                | IT 專案小組/AV 小組              |             | [購買](#procurement)                      |
| 網站準備             | 設施/AV 小組/IT 專案小組 |             | [網站準備](rooms-deploy.md#site-readiness)                      |
| 服務就緒性          | IT 專案小組                        |             | [服務就緒性](rooms-deploy.md#service-readiness)                      |
| Configuration              | IT 專案小組                        |             | [配置和部署](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | 設施/AV 小組/IT 專案小組 |             | [部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| 促進                   | 設施/AV 小組/IT 專案小組 |             | [促進](#plan-for-adoption-and-change-management)                      |
| 維護和作業 | AV 小組/IT 專案小組              |             | [管理概觀](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>會議室庫存與功能規劃

第一步是清點貴組織的現有會議與會議室，以瞭解他們的環境、會議室大小、版面配置及用途，並找出您想要的功能範圍中的每個會議室（例如哪些豐富的共同作業功能將在聊天室中啟用）。 

在每個現有的聊天室中建立一份裝置和功能的庫存之後，您在裝置選取規劃中將您的需求摘要放入規劃中，以建立豐富的會議解決方案。 除了空間大小和用途之外，每個聊天室都需要 (形式音訊、影片) ，除了房間大小和用途之外，所有人都扮演重要角色，決定哪一種方案最適合每個聊天室。 

在您的探索中，它是考慮房間雜訊和版面配置的關鍵所在。 例如，請確認房間中的椅子不會封鎖相機視圖。 確認會議室沒有過度回應或嘈雜的空調，且具有足夠的螢幕和 Microsoft 團隊聊天室功能。 考慮到您的音訊-視覺 (AV) 小組或合作夥伴將能提出建議，有許多因素要考慮。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>此部署的範圍內有哪些會議室？</li><li>哪些網站在您的部署範圍內？</li><li>誰將參與會議室庫存？</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>查看範圍中的會議室，並定義其適用的 Microsoft 團隊會議室配置。</li></ul>|

_會議/會議室庫存範例_

| 網站  | 會議室名稱 | 會議室類型 | 人數  | 在範圍中？ | 目前的會議室功能       | 未來的空間功能     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| 倫敦總部 | Curie         | 中型        | 6 &ndash; 12                  | 是          | 免持聽筒                        | 1畫面、音訊及影片加上簡報<br>PSTN 存取 |
| 悉尼總部 | 峰          | 大型         | 12 &ndash; 16                 | 是          | 舊版 AV 裝置，1個畫面與攝影機 | 2個畫面、音訊及影片加上簡報<br>PSTN 存取 |

## <a name="device-selection"></a>裝置選取 

根據您想要的會議室功能，評估哪些 Microsoft 團隊會議室方案最適合用於每個房間。 視房間大小和版面配置而定，決定哪種 AV 週邊裝置最適合。 

如需使用房間類型和大小的系統和週邊裝置類型指引，請參閱 [Microsoft 團隊會議室需求](requirements.md) 文章。 

根據您偏好的供應商，使用需求文章中提供的資訊來定義 Microsoft 團隊聊天室及每個會議室類型支援的週邊裝置設定，並將此作為您的部署範本。 

**Pro 提示** -某些會議室類型可能不適用於您的部署。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>從您的庫存中，哪些類型的會議室是在您的部署範圍內？</li><li>您會針對每個房間類型來部署哪些系統？</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始為您所選的系統收集重要的操作內容，並與您的購買小組取得聯繫。</li></ul>|

_針對貴組織的 Microsoft [小組聊天室] 部署範本範例_

| **房間類型/大小** | **人數**  | **Microsoft 團隊聊天室系統** | **週邊裝置**  | **顯示 (s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| 焦點 10 "x 9"      | 2 &ndash; 4                   |                                  |                         |                 |
| 小寫 16 "by 16"     | 4 &ndash; 6                   |                                  |                         |                 |
| 中等深淺 18 "x 20"    | 6 &ndash; 12                  |                                  |                         |                 |
| 大型 15 "by 32"     | 12 &ndash; 16                 |                                  |                         |                 |

**Pro 提示-** 現在是開始收集您所選之 Microsoft 團隊聊天室方案資訊的絕佳時機。

## <a name="procurement"></a>購買 

您可以透過裝置合作夥伴，透過套件或整合式解決方案來購買您所選的系統。 您也可以使用 Surface Pro 裝置以及現有且 _支援_ 的 AV 週邊裝置，來取得合作夥伴裝置停靠，並準備您自己的 Microsoft 團隊聊天室方案。 

您可以從 [ [需求] 文章](requirements.md)中所列的許多合作夥伴取得 Microsoft 團隊聊天室。 請造訪合作夥伴的網站，進一步瞭解這些解決方案和購買選項。 

視您的部署規模和方法而定，您可能會決定將 Microsoft 團隊聊天室和支援的週邊裝置運送到中央位置，以進行初始設定與作業。 這可能是在多個網站上分段式推出的好方法。 或者，您也可以選擇將捆綁套件直接傳送到您的網站。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您是否要將元件直接傳送到網站或轉移功能？</li><li>如果您決定使用一個) ，誰會管理轉移功能 (？</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>規劃作業。</li><li>規劃採納與變更管理。</li></ul>|

## <a name="plan-for-operations"></a>規劃作業 

您的組織必須持續執行監視、管理及管理工作，而且它也是在您的部署中提前進行這些工作的關鍵。 

許多組織有一個 AV 小組或管理其會議室和裝置的合作夥伴。 本小組應參與將管理 Microsoft 團隊聊天室裝置的人員同意，以進行監控效能，以及部署軟體更新與修復程式。 

考慮哪個支援人員佇列：您可以將 Microsoft 團隊 Rooms֪相關呼叫傳送給您，並提供支援人員小組的常見問題，讓他們能夠更清楚地瞭解如何使用 Microsoft 團隊聊天室，以及他們可以採取的主要疑難排解步驟。 此常見問題的良好起點是 [使用者](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 說明和 [已知問題](known-issues.md)。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理 Microsoft 團隊聊天室。</li><li>決定哪一台 [支援人員] 佇列將 Microsoft 團隊聊天室的相關呼叫路由。</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備主持帳戶。 </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>規劃採納與變更管理

Microsoft 團隊會議室系統會為您的使用者帶來新的功能。 您必須認識到這會對您的使用者進行變更，而且您應該確保您的行銷活動會識別新系統對您的使用者有何益處，而談話端點可用來與他們的小組共同進行討論的重要資訊。 

考慮在每個網站上排程顯示與告知事件與標牌刪除，以通知使用者新的功能。 您也可以在會議室中建立「快速入門手冊」。 請考慮在每個網站上尋找可協助其他人掌握速度並開始使用裝置的會議。
