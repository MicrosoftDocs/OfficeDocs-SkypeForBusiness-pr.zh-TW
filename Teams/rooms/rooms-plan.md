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
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 本文將說明部署新一代會議室系統Microsoft Teams 會議室相關的規劃考慮Skype考慮。
ms.openlocfilehash: f0b1f8797a8d1f9d7589e959c71699b1efd84e3c
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015223"
---
# <a name="plan-microsoft-teams-rooms"></a>規劃Microsoft Teams 會議室

本文將介紹一種端對端規劃、傳遞及操作Microsoft Teams 會議室作為整體會議與會議室策略的一部分。

您可以在下方找到規劃資訊，涵蓋建議的方法和您需要做出的重要決策，以及支援技術資訊的連結。 即使您已經完全部署，我們建議您查看規劃、部署及管理節。

## <a name="overview-of-microsoft-teams-rooms"></a>概觀Microsoft Teams 會議室

Microsoft Teams 會議室提供完整的會議體驗，將 HD 視音訊、音訊和內容共用帶到各種大小的會議，從小型活動區域到大型會議室。

![使用者點Teams 會議室主控台，背景為顯示器。](../media/room-systems-image1.jpg "使用者點Teams 會議室主控台，背景為顯示器") 
[Microsoft Teams 會議室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)是一個很好的資源，可進一Microsoft Teams 會議室瞭解如何為您的部署增添價值。

## <a name="microsoft-teams-rooms-components"></a>Microsoft Teams 會議室元件

Microsoft Teams 會議室包含下列關鍵元件，以提供出色的使用者體驗：

- 觸控螢幕主控台
- 計算模組
- Microsoft Teams 會議室應用程式
- 外接裝置 (、麥克風、喇叭) 
- 外部畫面 (最多兩) 
- HDMI 輸入

您可以從許多廠商購買這些元件做為預先安裝套件，也可以按照本文中記載的需求個別購買支援 [的元件](requirements.md)。

您可以使用內部Microsoft Teams 會議室部署Microsoft Teams部署商務用 Skype部署。  請參閱Teams 會議室[授權更新](rooms-licensing.md)，以瞭解所需授權的資訊。

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![決定部署。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您是否將部署Microsoft Teams 會議室組織？ </li><li>您將如何取得Microsoft Teams 會議室系統？</li></ul> |
| ![識別活動。](../media/audio_conferencing_image9.png)<br/>後續步驟 | <ul><li>識別誰將在整個部署期間進行重要活動。</li><li>查看您 (會議室，並規劃) ，以瞭解您想要在哪裡部署 Microsoft Teams 會議室，以及適合會議室大小的周邊裝置。</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>識別誰將在整個部署期間進行重要活動

使用下列方法引導您完成部署，並自訂您組織所需的範例輸出。

首先瞭解您擁有哪些會議室，並構想未來最適合您的會議室，然後選取並購買所需的設備、準備網站、配置及部署服務、管理變更和使用者採用，以及開發作業和維護程式。

![首先瞭解您擁有的內容，並構想最適合您的專案，然後選取並購買您所需的設備、準備網站、配置及部署服務、管理變更和使用者採用，以及開發作業和維護程式。](../media/room-systems-image2.png "首先瞭解您擁有的內容，並構想最適合您的專案，然後選取並購買您所需的設備、準備網站、配置及部署服務、管理變更和使用者採用，以及開發作業和維護程式。")

您可能需要跨多個小組協調這些活動。 我們會提供您應涵蓋之主要活動的高層級視圖，以及一般參與部署和管理會議室系統的團隊建議，説明您決定需要處理哪些人。

| 工作                       | 神秘承擔工作           | 已指派給 | 此內容的連結 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 庫存會議室            | 設施/ AV 團隊 / IT Project團隊 |             | [會議室庫存與功能規劃](#room-inventory-and-capability-planning)        |
| 規劃功能          | IT Project小組                        |             | [會議室庫存與功能規劃](#room-inventory-and-capability-planning)                       |
| 裝置選取範圍           | IT Project團隊 / AV 團隊              |             | [裝置選取範圍](#device-selection)                      |
| 採購                | IT Project團隊 / AV 團隊              |             | [採購](#procurement)                      |
| 網站準備就緒             | 設施/ AV 團隊 / IT Project團隊 |             | [網站準備就緒](rooms-deploy.md#site-readiness)                      |
| 服務整備          | IT Project小組                        |             | [服務整備](rooms-deploy.md#service-readiness)                      |
| 配置              | IT Project小組                        |             | [組配置與部署](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | 設施/ AV 團隊 / IT Project團隊 |             | [部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| 採用                   | 設施/ AV 團隊 / IT Project團隊 |             | [採用](#plan-for-adoption-and-change-management)                      |
| 維護和作業 | AV 小組/IT Project小組              |             | [管理概觀](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>會議室庫存與功能規劃

第一個步驟是清點貴組織現有的會議空間和會議室，以瞭解其環境、會議室大小、版面配置及用途。 接著，您可以找出您希望每個會議室擁有的功能，例如智慧型相機、白板、內容相機等。

建立每個現有會議室之設備與功能的庫存之後，該會議室的需求會進入您的裝置選擇規劃，以建立豐富的會議解決方案。 除了會議室 (用途) ，每個會議室所需的音訊、視) 模式，在決定最適合每個會議室的解決方案時，都扮演重要角色。 

做為探索的一部分，考慮會議室的隔音和版面配置是一項關鍵。 例如，檢查會議室中的椅子是否無法封鎖相機的視野。 確認會議室沒有過度回音或吵雜的空調，而且其螢幕和Microsoft Teams 會議室。 有許多因素可考慮您的視 (視) 小組或合作夥伴可以提供意見。 

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![deplyment rooms。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>在範圍中檢查會議室，並定義Microsoft Teams 會議室的會議室配置。</li></ul>|

_範例會議/會議室庫存_

| 網站  | 會議室名稱 | 會議室類型 | 人員數目  | 在範圍中？ | 目前的會議室功能       | 未來的會議室功能     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| 倫敦總部 | 居裡         | 中型        | 6 &ndash; 12                  | 是          | 揚聲器                        | 1 個螢幕、音訊和視音訊加簡報<br>PSTN Access |
| 雪梨總部 | 山          | 大型         | 12 &ndash; 16                 | 是          | 舊版 AV 裝置、1 個螢幕和相機 | 2 個畫面、音訊和視音訊以及簡報<br>PSTN Access |

## <a name="device-selection"></a>裝置選取範圍 

根據Microsoft Teams 會議室未來功能，評估哪一種解決方案最適合每個會議室。 根據會議室大小和版面配置，決定最適合的 AV 周邊裝置。 

有關如何根據會議室類型和大小來瞭解系統與周邊裝置類型的指南，請參閱Microsoft Teams 會議室[一文](requirements.md)。 

根據您偏好的廠商，使用需求文章中提供的資訊，定義每個會議室類型的 Microsoft Teams 會議室 和支援的周邊裝置組組，並使用此範本做為您的部署範本。 

**Pro提示**- 某些會議室類型可能不適用於您的部署。

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![範圍中的會議室。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>從庫存中，哪些類型的會議室適用于您的部署？</li><li>您將針對每個會議室類型部署哪些系統？</li></ul>|
| ![收集材料。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始收集所選系統的重要作業資料，並吸引您的採購小組參與。</li></ul>|

_貴Microsoft Teams 會議室部署範本範例_

| **會議室類型/大小** | **人員數目**  | **Microsoft Teams 會議室系統** | **周邊裝置**  | **顯示 ()** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| 焦點 10' 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Small 16' by 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| 中 18' 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| 大型 15' 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Pro秘訣 –** 現在是開始收集您所選Microsoft Teams 會議室解決方案相關資訊的很好時間。

## <a name="procurement"></a>採購 

您可以透過裝置合作夥伴，以套件或整合解決方案購買您選擇的系統。

您可以向Microsoft Teams 會議室一文中列出的許多合作夥伴取得[產品資訊](requirements.md)。 請流覽合作夥伴的網站，深入瞭解這些解決方案和採購選項。 

根據您的部署規模和方式，您可能會決定將Microsoft Teams 會議室和支援的周邊裝置運送至中央位置，進行初始組組和指派。 這可能是跨多個網站進行階段部署的好方法。 或者，您可以選擇直接將套件出貨至網站。 

|   &nbsp; |  &nbsp;   |
|-----------|------------|
| ![出貨元件。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您是否將元件直接出貨至網站或暫存設施？</li><li>神秘您決定使用一個 (，將會管理暫存) ？</li></ul>|
| ![計畫作業。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>規劃作業。</li><li>規劃採用和變更管理。</li></ul>|

## <a name="plan-for-operations"></a>規劃作業 

貴組織必須持續執行監控、系統管理及管理工作，且必須同意誰在部署初期承擔這些工作。 

許多組織都有一個 AV 小組或合作夥伴，負責管理其會議室和裝置。 或者，您可以利用 Microsoft Teams 會議室，協助管理Microsoft Teams 會議室進階版。 決定誰將管理Microsoft Teams 會議室裝置，以監控績效，以及部署軟體更新和 hotfix。 

考慮您將路由 Microsoft Teams 會議室 相關通話至哪個服務台佇列，並提供常見問題給技術支援小組，以便他們進一步瞭解如何使用 Microsoft Teams 會議室，以及他們可以採取的主要疑難排解步驟。 此常見問題的一個好起點是[使用者説明和](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)[已知問題](known-issues.md)。

|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![選擇管理員。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理Microsoft Teams 會議室。</li><li>決定要路由與Microsoft Teams 會議室通話的服務台佇列。</li></ul>|
| ![準備主機帳戶。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備託管帳戶。 </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>規劃採用與變更管理

Microsoft Teams 會議室系統會為使用者介紹新功能。 您必須瞭解這將會為使用者帶來變更，而且您應該確保您的內部行銷活動識別新系統會為使用者帶來的好處，以及潛在客戶可以用來與小組討論的關鍵重點。 

請考慮在每個網站排程顯示與通知活動與海報丟包，以告知使用者新功能。 您也可以在聊天室中建立「快速入門手冊」。 請考慮在每個網站尋找會議支援者，協助其他人快速上手並開始使用裝置。
