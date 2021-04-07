---
title: 管理內容共用的會議策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
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
description: 瞭解如何在 Teams 中管理會議策略設定以共用內容。
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598713"
---
# <a name="meeting-policy-settings---content-sharing"></a>會議策略設定 - 內容共用

<a name="bkcontentsharing"> </a>

本文將說明下列與內容共用相關的會議策略設定：

- [螢幕畫面分享模式](#screen-sharing-mode)
- [允許參與者提供或要求控制權](#allow-a-participant-to-give-or-request-control)
- [允許外部參與者提供或要求控制權](#allow-an-external-participant-to-give-or-request-control)
- [允許 PowerPoint 共用](#allow-powerpoint-sharing)
- [允許白板](#allow-whiteboard)
- [允許共用筆記](#allow-shared-notes)

## <a name="screen-sharing-mode"></a>螢幕畫面分享模式

此設定是每個召集人和每個使用者策略的組合。 此設定可控制使用者會議是否允許桌面和視窗共用。 未指派任何策略的會議 (例如匿名、來賓、B2B 和) 繼承會議召集人的政策。

|設定值 |行為  |
|---------|---------|
|**整個畫面**    | 會議允許完整桌面共用和應用程式共用 |
|**單一應用程式**   | 會議允許應用程式共用        |
|**禁用**     |會議已關閉螢幕畫面共用和應用程式共用。       |

讓我們來看看下列範例。

|使用者 |會議原則 |螢幕畫面分享模式 |
|---------|---------|---------|
|Daniela  | 全域   | 整個畫面 |
|艾曼達   | 位置1MeetingPolicy  | 禁用 |

Daniela 主持的會議允許會議參與者共用其整個螢幕或特定應用程式。 如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定應用程式，因為她的政策設定已停用。 在由 Amanda 主持的會議中，不允許任何人共用其螢幕或單一應用程式，無論指派給他們的螢幕共用模式政策如何。  因此，Daniela 無法共用她的螢幕或單一應用程式在 Amanda 的會議中。  

目前，如果使用者使用的是 Google Chrome，他們無法在 Teams 會議中播放影片或共用螢幕畫面。

## <a name="allow-a-participant-to-give-or-request-control"></a>允許參與者提供或要求控制權

此設定是每個使用者的策略。 此設定可控制使用者是否可以將共用桌面或視窗的控制權授予其他會議參與者。 若要提供控制權，請將游標停留在畫面頂端。

如果使用者已開啟此設定，共用會話中的頂端列會顯示提供控制項選項。

![顯示給予控制權選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

如果使用者的設定已關閉，則無法使用提供 **控制項** 選項。

![顯示沒有提供控制權選項的螢幕擷取畫面](media/meeting-policies-give-control-not-available.png)

讓我們來看看下列範例。

|使用者 |會議原則  |允許參與者提供或要求控制權 |
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|巴別克    | 位置1MeetingPolicy        | 關閉   |

Daniela 可以將共用桌面或視窗的控制權授予由巴可克組織之會議的其他參與者。 不過，巴別克無法將控制權授予其他參與者。

若要使用 PowerShell 來控制誰可以給予控制權或接受控制權要求，請使用 AllowParticipantGiveRequestControl Cmdlet。

> [!NOTE]
> 若要在共用期間提供並控制共用內容，雙方必須使用 Teams 桌面用戶端。 當任一方執行瀏覽器中的 Teams 時，則不支援控制。 這是我們正計畫修正的技術限制所造成。

## <a name="allow-an-external-participant-to-give-or-request-control"></a>允許外部參與者提供或要求控制權

此設定是每個使用者的策略。 無論組織是否已為使用者設定此策略，無論會議召集人已設定什麼內容，外部參與者都可以執行哪些操作。 此參數可控制外部參與者是否可以根據共用者在其組織會議政策中設定的內容，獲得控制權或要求控制共用者螢幕。 Teams 會議中的外部參與者可以分類為：  

- 匿名使用者
- 來賓使用者  
- B2B 使用者
- 聯合使用者  

在共用時，聯合使用者是否可以提供控制權給外部使用者，是由允許外部參與者在組織中提供或要求控制權設定所控制。

若要使用 PowerShell 控制外部參與者是否可以提供控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。

### <a name="allow-powerpoint-sharing"></a>允許 PowerPoint 共用

這是每個使用者的政策。 此設定可控制使用者是否可以共用會議中的 PowerPoint 幻燈片組。 外部使用者 ，包括匿名、來賓和聯盟使用者，會繼承會議召集人的政策。

讓我們來看看下列範例。

|使用者 |會議原則  |允許 PowerPoint 共用 |
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|艾曼達   | 位置1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，也無法共用會議中 PowerPoint 的幻燈片組。 即使會議是由 Amanda 組織，Daniela 也可以共用 PowerPoint 幻燈片組。 Amanda 可以查看會議中其他人共用的 PowerPoint 幻燈片組，即使她無法共用 PowerPoint 幻燈片組。

## <a name="allow-whiteboard"></a>允許白板

此設定是每個使用者的策略。 此設定可控制使用者是否可以在會議共用白板。 外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。

讓我們來看看下列範例。

|使用者 |會議原則  |允許白板|
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|艾曼達   | 位置1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，也無法共用會議中的白板。 即使會議是由 Amanda 組織，Daniela 也可以共用白板。  

## <a name="allow-shared-notes"></a>允許共用筆記

此設定是每個使用者的策略。 此設定可控制使用者是否可以在會議建立及共用筆記。 外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。 目前 **只有** 少於 20 個參與者的會議支援會議筆記選項卡。

讓我們來看看下列範例。

|使用者 |會議原則  |允許共用筆記 |
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|艾曼達   | 位置1MeetingPolicy | 關閉 |

Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。




## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](assign-policies.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議政策](meeting-policies-restricted-anonymous-access.md)
