---
title: 管理內容共用的會議策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: 瞭解如何在共用內容Teams管理會議策略設定。
ms.openlocfilehash: 6c713800aa0f95c7adfd6655455e6ff332f91595
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205313"
---
# <a name="meeting-policy-settings---content-sharing"></a>會議原則設定 - 內容共用

<a name="bkcontentsharing"> </a>

本文將說明下列與內容共用相關的會議策略設定：

- [螢幕畫面分享模式](#screen-sharing-mode)
- [允許參與者授與或要求控制權](#allow-a-participant-to-give-or-request-control)
- [允許外部參與者授與或要求控制權](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint共用](#powerpoint-sharing)
- [Whiteboard](#whiteboard)
- [共用筆記](#shared-notes)

## <a name="screen-sharing-mode"></a>螢幕畫面分享模式

此設定是每個召集人和每個使用者策略的組合。 此設定可控制使用者會議是否允許桌面和視窗共用。 未獲指派任何原則的會議參與者 (例如匿名、來賓、B2B 和同盟參與者) 會繼承會議召集人的原則。

|設定值 |行為  |
|---------|---------|
|**整個螢幕**    | 會議中允許完整桌面共用和應用程式共用 |
|**單一應用程式**   | 會議中允許應用程式共用        |
|**已停用**     |會議中已關閉螢幕畫面分享和應用程式共用。       |

讓我們看看下列範例。

|使用者 |會議原則 |螢幕畫面分享模式 |
|---------|---------|---------|
|Daniela  | 全域   | 整個螢幕 |
|Amanda   | Location1MeetingPolicy  | 已停用 |

由 Daniela 主持的會議會允許會議參與者共用其整個螢幕或特定應用程式。 如果 Amanda 加入 Daniela 的會議，Amanda 會無法分享她的螢幕畫面或特定應用程式，因為她的原則設定已停用。 在 Amanda 主持的會議中，任何人都不被允許共用其螢幕畫面或單一應用程式，而無論指派給他們的螢幕畫面分享模式原則為何。  因此，Daniela 無法共用她的螢幕或單一應用程式在 Amanda 的會議中。  

目前，如果使用者使用 Google Chrome，他們無法在 Teams 會議中播放視訊或分享其螢幕畫面。

## <a name="allow-a-participant-to-give-or-request-control"></a>允許參與者授與或要求控制權

此設定是每個使用者的策略。 此設定可控制使用者是否可以將共用桌面或視窗的控制權授與其他會議參與者。 若要授與控制權，請將游標停留在畫面上方。

如果已為使用者開啟此設定，則共用工作階段上方列中會顯示 [授與控制權 **]** 選項。

![顯示 [授與控制權] 選項的螢幕擷取畫面。](media/meeting-policies-give-control.png)

如果已為使用者關閉該設定，則無法使用 **[授與控制權]** 選項。

![顯示 [授與控制權] 選項無法使用的螢幕擷取畫面。](media/meeting-policies-give-control-not-available.png)

讓我們看看下列範例。

|使用者 |會議原則  |允許參與者授與或要求控制權 |
|---------|---------|---------|
|Daniela   | 全域   | 開啟       |
|Babek    | Location1MeetingPolicy        | 關閉   |

Daniela 可以將共用桌面或視窗的控制權授予由巴可克組織之會議的其他參與者。 不過，巴別克無法將控制權授予其他參與者。

若要使用 PowerShell 來控制誰可以授與控制權或接受控制的要求，請使用 AllowParticipantGiveRequestControl Cmdlet。

> [!NOTE]
> 若要在共用期間提供和控制共用內容，雙方都必須使用 Teams 電腦版用戶端。 當任一方執行瀏覽器中的 Teams 時，則不支援控制。 這是我們正計畫修正的技術限制所造成。

## <a name="allow-an-external-participant-to-give-or-request-control"></a>允許外部參與者授與或要求控制權

此設定是每個使用者的策略。 無論會議召集人已設定什麼專案，組織是否為使用者設定此策略，都無法控制外部參與者可以執行什麼操作。 此參數會根據分享者在其組織的會議原則中所設定的內容，是否可以授與外部參與者控制或要求控制分享者的螢幕畫面。 Teams 會議的外部參與者可依如下分類：  

- 匿名使用者
- 來賓使用者  
- B2B 使用者
- 同盟使用者  

同盟使用者是否可以在分享時將控制授與外部使用者是由其組織中的 [允許外部參與者授與或要求控制權 **]** 設定控制。

若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制的要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。

### <a name="powerpoint-sharing"></a>PowerPoint共用

這是每一使用者原則。 此設定可控制使用者是否可以在會議中分享 PowerPoint 投影片組。 外部使用者 (包括匿名、來賓和同盟使用者) 會繼承會議召集人的原則。

讓我們看看下列範例。

|使用者 |會議原則  |PowerPoint共用 |
|---------|---------|---------|
|Daniela   | 全域   | 開啟       |
|Amanda   | Location1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，也無法在會議中分享 PowerPoint 投影片組。 即使會議是由 Amanda 召集，Daniela 也可以分享 PowerPoint 投影片組。 Amanda 可以檢視其他人在會議中分享的 PowerPoint 投影片組，不過她無法分享 PowerPoint 投影片組。

## <a name="whiteboard"></a>Whiteboard

此設定是每個使用者的策略。 此設定可控制使用者是否可以在會議中分享白板。 外部使用者 (包括匿名、B2B 和同盟使用者) 會繼承會議召集人的原則。

讓我們看看下列範例。

|使用者 |會議原則  |Whiteboard|
|---------|---------|---------|
|Daniela   | 全域   | 開啟       |
|Amanda   | Location1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，也無法分享會議中的白板。 即使會議是由 Amanda 召集，Daniela 也可以分享白板。  

## <a name="shared-notes"></a>共用筆記

此設定是每個使用者的策略。 此設定可控制使用者是否可以在會議中建立和共用記事。 外部使用者 (包括匿名、B2B 和同盟使用者) 會繼承會議召集人的原則。 目前 **只有** 少於 20 個參與者的會議才支援會議筆記選項卡。

讓我們看看下列範例。

|使用者 |會議原則  |共用筆記 |
|---------|---------|---------|
|Daniela   | 全域   | 開啟       |
|Amanda   | Location1MeetingPolicy | 關閉 |

Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄任何筆記。




## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](policy-assignment-overview.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議原則](meeting-policies-restricted-anonymous-access.md)
