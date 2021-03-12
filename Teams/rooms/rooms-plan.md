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
description: 本文將說明部署 Microsoft Teams 會議室的相關規劃考慮，這是新一代的 Skype 會議室系統。
ms.openlocfilehash: fae50e076467efdfe69115d967f3d6564ba9266a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726274"
---
# <a name="plan-microsoft-teams-rooms"></a>規劃 Microsoft Teams 會議室

本文將介紹一種端對端的方法來規劃、提供及操作 Microsoft Teams 會議室，做為整體會議與會議室策略的一部分。

您可以在下方找到規劃資訊，涵蓋建議的方法和您需要做出的重要決策，以及支援技術資訊的連結。 即使您已完全部署，我們建議您查看計畫、部署及管理節。

## <a name="overview-of-microsoft-teams-rooms"></a>Microsoft Teams 會議室概觀

Microsoft Teams 會議室提供完整的會議體驗，將 HD 視、音訊和內容共用功能帶到各種大小的會議，從小型擠在一起的區域到大型會議室。

![安裝在會議室牆面的主機、麥克風和大型螢幕，說明 Microsoft Teams 會議室設定範例的元素。](../media/room-systems-image1.png "安裝在會議室牆面的主機、麥克風和大型螢幕，說明 Microsoft Teams 會議室設定範例的元素。")

[Microsoft Teams 會議室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 是一項很棒的資源，可進一瞭解更多資訊 Microsoft Teams 會議室，以及如何在部署中新增值。 此外，我們建議您觀看此概 [觀影片](https://youtu.be/tNey5KZVCl0)。 

## <a name="microsoft-teams-rooms-components"></a>Microsoft Teams 會議室元件

Microsoft Teams 會議室包含下列重要元件，以提供出色的使用者體驗：

- 觸控螢幕控制台
- 計算
- Microsoft Teams 會議室應用程式
- 擴充座/擴充器
- 周邊裝置 (、麥克風、喇叭) 
- 外部螢幕 (最多兩) 
- HDMI 輸入

您可以將這些元件採購為預先安裝的產品群組，也可以按照本文中說明的需求個別購買 [支援的元件](requirements.md)。

除了 Surface Pro/dock 組合之外，您也可以購買整合觸控螢幕控制台、計算、固定和重要周邊裝置之 Microsoft Teams 會議室。 

一般來說，套件和整合式裝置包含預先安裝的軟體，而如果您個別為 Surface Pro 系統購買支援的元件，則需要安裝軟體。 有關在 [裝置上安裝軟體的指示，請參閱這篇文章](rooms-scale.md)。 

您可以使用 Microsoft Teams、商務用 Skype Online 或商務用 Skype 混合式或內部部署來部署 Microsoft Teams 會議室。  請參閱 [Teams 會議室授權更新](rooms-licensing.md) ，以尋找所需授權的資訊。

|    |     |
|-----------|------------|
|![決定部署](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您將在組織中部署 Microsoft Teams 會議室嗎？ </li><li>您將如何採購 Microsoft Teams 會議室系統，以獨立元件或整合式單位進行統合？</li></ul> |
| ![識別活動](../media/audio_conferencing_image9.png)<br/>後續步驟 | <ul><li>找出將在整個部署期間進行重要活動的人。</li><li>請查閱您 (的會議室，並規劃設定) ，以瞭解您想要在哪裡部署 Microsoft Teams 會議室，以及適合會議室大小的周邊裝置。</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>識別哪些人會在整個部署期間進行重要活動

使用下列說明的方法來引導您完成部署，並自訂這些文章中針對貴組織所提供的範例輸出。

首先，先瞭解您擁有哪些會議室，並想像未來最適合您的會議室，然後選取並更新您所需的設備、準備網站、配置及部署服務、管理變更和使用者採用，以及開發作業和維護程式。

![首先，先瞭解您擁有的內容，並想像最適合您的專案，然後選取並更新您所需的設備、準備網站、配置及部署服務、管理變更和使用者採用，以及開發作業和維護程式。](../media/room-systems-image2.png "首先，先瞭解您擁有的內容，並想像最適合您的專案，然後選取並更新您所需的設備、準備網站、配置及部署服務、管理變更和使用者採用，以及開發作業和維護程式。")

您可能需要跨多個小組協調這些活動。 我們會提供您應涵蓋之主要活動的高層級觀點，以及一般參與部署及管理會議室系統的團隊建議，説明您決定需要處理哪些人。

| 工作                       | 誰可能負責這項工作           | 指派給 | 此內容的連結 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 庫存會議室            | 設施/AV 小組/IT 專案小組 |             | [會議室庫存與功能規劃](#room-inventory-and-capability-planning)        |
| 規劃功能          | IT 專案小組                        |             | [會議室庫存與功能規劃](#room-inventory-and-capability-planning)                       |
| 裝置選取範圍           | IT 專案小組/AV 小組              |             | [裝置選取範圍](#device-selection)                      |
| 採購                | IT 專案小組/AV 小組              |             | [採購](#procurement)                      |
| 網站就緒             | 設施/AV 小組/IT 專案小組 |             | [網站就緒](rooms-deploy.md#site-readiness)                      |
| 服務整備          | IT 專案小組                        |             | [服務整備](rooms-deploy.md#service-readiness)                      |
| 配置              | IT 專案小組                        |             | [組配置與部署](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | 設施/AV 小組/IT 專案小組 |             | [部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| 採用                   | 設施/AV 小組/IT 專案小組 |             | [採用](#plan-for-adoption-and-change-management)                      |
| 維護和作業 | AV 小組 /IT 專案小組              |             | [管理概觀](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>會議室庫存與功能規劃

第一個步驟是清點貴組織現有的會議室，以瞭解其環境、會議室大小、版面配置及用途，並找出您希望未來範圍內每個會議室擁有的功能，例如會議室中將啟用哪些更豐富的共同合作功能。 

在您建立每個現有會議室之設備與功能的庫存之後，該會議室的饋送需求會納入您的裝置選擇規劃，以建立豐富的會議解決方案。 每個 (所需的音訊、視) 形式 ，除了會議室大小和用途之外，在決定哪個解決方案最適合每個會議室時，都扮演重要角色。 

做為探索的一部分，考慮會議室設計與版面配置是一項關鍵。 例如，檢查會議室中的椅子不會封鎖攝影機的視野。 確認會議室沒有多餘的回音或噪音，而且有足夠的電力供螢幕和 Microsoft Teams 會議室使用。 有許多因素可考慮您的音訊及視 (視) 團隊或合作夥伴將可提供意見。 

|    |     |
|-----------|------------|
| ![deplyment 會議室](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>在範圍中檢查會議室，並定義 Microsoft Teams 會議室的組配置。</li></ul>|

_範例會議/會議室庫存_

| 網站  | 會議室名稱 | 會議室類型 | 人數  | 範圍中？ | 目前的會議室功能       | 未來的會議室功能     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| 倫敦總部 | 居裡         | 中型        | 6 &ndash; 12                  | 是          | 揚聲器                        | 1 個螢幕、音訊和視音訊加簡報<br>PSTN Access |
| 雪梨總部 | 山          | 大型         | 12 &ndash; 16                 | 是          | 舊版 AV 裝置、1 個螢幕和相機 | 2 個畫面、音訊和視視以及簡報<br>PSTN Access |

## <a name="device-selection"></a>裝置選取範圍 

根據您想要的會議室未來功能，評估哪個 Microsoft Teams 會議室解決方案最適合每個會議室。 根據會議室大小和版面配置，決定最適合的 AV 周邊裝置。 

請參閱 Microsoft Teams 會議室需求文章，以根據會議室類型和大小來瞭解系統及周邊裝置[類型。](requirements.md) 

根據您偏好的廠商，使用需求文章提供的資訊來定義您的 Microsoft Teams 會議室，以及每個聊天室類型支援的周邊裝置組配置，並使用此範本做為您的部署範本。 

**專業提示** – 某些聊天室類型可能不適用於您的部署。

|    |     |
|-----------|------------|
| ![範圍中的會議室](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>從庫存中，您的部署範圍中會提供哪些類型的會議室？</li><li>您將針對每種聊天室類型部署哪些系統？</li></ul>|
| ![收集材料](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始收集所選系統的重要營運資料，並吸引您的採購小組參與。</li></ul>|

_貴組織的 Microsoft Teams 會議室部署範本範例_

| **會議室類型/大小** | **人數**  | **Microsoft Teams 會議室系統** | **周邊裝置**  | **顯示 ()** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| 焦點 10' by 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Small 16' by 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| 中 18' by 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| Large 15' by 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**專業秘訣 –** 現在是開始收集您所選 Microsoft Teams 會議室解決方案相關資訊的一個很好的時間。

## <a name="procurement"></a>採購 

您可以透過裝置合作夥伴將您選擇的系統採購為套件或整合式解決方案。 您也可以使用 Surface Pro 裝置和現有支援的 _AV_ 周邊裝置，取得合作夥伴裝置 Dock 並準備您自己的 Microsoft Teams 會議室解決方案。 

您可從需求文章中列出的許多合作夥伴取得 Microsoft Teams [會議室](requirements.md)。 請流覽合作夥伴的網站，以深入瞭解這些解決方案和採購選項。 

根據您的部署規模和方式，您可能會決定將 Microsoft Teams 會議室和支援的周邊裝置運送到集中位置，進行初始組配置和指派。 對於跨多個網站進行階段部署來說，這可能是一個好方法。 或者，您可以選擇將方案直接出貨到網站。 

|    |     |
|-----------|------------|
| ![出貨元件](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您是否將元件直接出貨至網站或暫存設施？</li><li>如果您決定使用一個 (，誰將管理臨時) ？</li></ul>|
| ![計畫作業](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>規劃作業。</li><li>規劃採用和變更管理。</li></ul>|

## <a name="plan-for-operations"></a>規劃作業 

貴組織必須持續執行監控、系統管理及管理工作，而且必須儘早同意由誰在部署時執行這些工作。 

許多組織都有管理其會議室和裝置之 AV 團隊或合作夥伴。 這個小組應參與同意由誰管理 Microsoft Teams 會議室裝置，以監控績效，以及部署軟體更新和 Hotfix。 

請考慮將 Microsoft Teams Rooms֪ 相關通話路由至哪一個技術支援人員佇列，並提供常見問題給支援人員小組，以便他們進一步瞭解如何使用 Microsoft Teams 會議室，以及可採取的重要疑難排解步驟。 這個常見問題的一個好起點是 [使用者説明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 和 [已知問題](known-issues.md)。

|    |     |
|-----------|------------|
| ![選擇管理員](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定管理 Microsoft Teams 會議室的人。</li><li>決定要路由 Microsoft Teams 會議室相關通話的技術支援人員佇列。</li></ul>|
| ![準備主機帳戶](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備託管帳戶。 </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>規劃採用與變更管理

Microsoft Teams 會議室系統會為使用者介紹新功能。 您必須瞭解這將會為使用者帶來變更，而且您應該確保您的行銷活動找出新系統將為使用者提供的好處，以及主要談話重點潛在客戶可用來與小組討論。 

請考慮在每個網站排程放映和通知活動與海報，以告知使用者新功能。 您也可以在聊天室中建立「快速入門手冊」。 請考慮在每個網站上尋找可協助其他人快速上手並開始使用裝置的會議支援者。
