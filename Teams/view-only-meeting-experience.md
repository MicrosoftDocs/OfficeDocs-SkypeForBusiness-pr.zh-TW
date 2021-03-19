---
title: 僅查看會議體驗
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解系統管理員、簡報者和出席者的 Teams 僅查看會議體驗
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf6787c3118ba36b71175f0ddb3360e980732a71
ms.sourcegitcommit: 71b9b5ec80014bd25758493bc06d633c4eac735c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50867062"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 只能查看會議體驗

> [!Note]
> Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中將提供僅觀看廣播。 此功能將于 2021 年 3 月 1 日啟用為預設關閉。 Microsoft 365 政府版 G3/G5 方案中的這項功能將于稍後提供。 如果您想要將功能預設為 ON，您必須在此日期之後變更預設政策。 使用 PowerShell 啟用該策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` 。

> [!Note]
> 如果您的會議或網路研討會達到容量，Teams 將會順暢地縮放，以容納 10，000 人只能觀看的廣播體驗。 此外，在增加遠端工作的這一期間，利用今年底甚至超過 20，000 人的廣播。

Microsoft Teams 最多允許 10，000 位出席者加入 Teams 會議。 達到主要會議的容量後，其他出席者將會加入，並享有只能觀看的體驗。

第一次加入會議的出席者，最多達會議容量，將會獲得完整的 Teams 會議體驗。 他們可以共用音訊和視音訊、查看共用影片，以及參與會議聊天。

到達主要會議容量後加入的出席者將享有僅以視圖顯示的體驗。

我們有完整的 Android 和 iOS 行動支援，讓出席者加入。

> [!Note]
> 目前，在 WW 中可以聊天和通話的會議人數上限為 300 人，GCC、GCC High 和 DoD 為 250 人。

任何擁有 E3/E5/A3/A5 SKU 的召集人，預設會停用僅顯示模式體驗。 不需要進一步設定或設定。

## <a name="disable-teams-view-only-experience"></a>停用 Teams 只能查看體驗

系統管理員可以使用 PowerShell 停用僅查看體驗。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

未來，系統管理員也可以停用 Teams 系統管理中心中的僅查看體驗。

## <a name="impact-to-users"></a>對使用者的影響

使用者的體驗會因數個因素而異。

當達到主要會議的容量時，如果下列任一項為 True，出席者將無法加入會議：

- 系統管理員已停用 Teams 只能查看體驗。
- 出席者沒有跳過大廳的許可權。

當達到主要會議的容量時，會議召集人和簡報者會看到橫幅，告知他們會議容量已達，且新的出席者會加入僅觀看的出席者。

  ![適用于召集人和簡報者的 Teams 用戶端和橫幅訊息](media/chat-and-banner-message.png)

當達到主要會議的容量時，會議出席者會以加入前畫面通知他們以僅查看模式加入。

  ![Teams 加入前畫面，以及參與者的訊息，告知他們將以僅以模式加入](media/view-only-pre-join-screen.png)

如果有空間，使用者一定會加入主會議。 如果主要會議達到容量，且一或多個出席者離開主會議，則主會議具有可用的容量。 加入會議 (或重新加入) 出席者會加入主會議，直到會議再次達到容量。 只有使用模式體驗的出席者不會自動升級至主要會議，目前無法手動升級至主要會議。

如果尚未設定簡報者/出席者角色，主會議的空格會以先到先得為基礎填入。 達到會議容量後，所有其他使用者都會以僅以視圖為體驗加入會議。

## <a name="impact-to-meeting-presenters"></a>對會議簡報者的影響

會議簡報者的限制包括：

- 您沒有僅查看出席者的資訊。 我們不支援僅供出席者使用 E-discovery。
- 使用者無法看到僅查看出席者。
- 您無法從會議移除只能查看的出席者。

> [!Note]
> 出席者計數只會反映會議中的人員，而非僅顯示會議室中的人員。 因此，簡報者無法確切計算誰在僅觀看體驗中。

## <a name="experience-for-view-only-attendees"></a>只有觀看的出席者體驗

Teams 只能查看體驗可讓出席者：

- 聆聽 Teams 主要會議的參與者。
- 如果使用中喇叭正在共用視 (，請參閱使用中喇叭) 。
- 查看使用共用桌面功能共用的內容。

只有觀看的出席者將無法在會議中體驗下列選項：

- 如果出席者沒有許可權根據設定大廳政策或選項來跳過大廳，請加入會議。
- 使用音訊會議加入唯一的會議室。
- 使用 Microsoft Teams Room 系統，或使用雲端視 (CVI) 聊天室。
- 分享他們的音訊或視音訊。
- 查看或參與會議聊天。
- 請參閱會議參與者的視音訊源，除非參與者是使用中的演講者。
- 請參閱使用原生共用 PowerPoint 功能共用的 PowerPoint 檔案，或桌面共用功能 (個別應用程式共用) 。

## <a name="view-only-feature-limitations"></a>僅查看功能限制

- 無論會議的即時字幕設定如何，只有視點出席者一定會看到即時字幕。 目前僅支援英文標題。
- 串流技術會支援僅觀看的出席者。
- 出席報告不會包含僅顯示出席者。
- 僅觀看的出席者將享有單一影片體驗。 他們可以看到使用中的喇叭或正在共用的內容，但無法同時看到兩者。
- 我們目前不支援僅供出席者使用圖庫、大型圖庫或共同模式版面配置。   
- 僅查看出席者與一般出席者不會有相同的延遲。 <sup>1</sup>

  <sup>1</sup> 僅觀看的出席者將在會議進行 30 秒的視像和音訊延遲。  
