---
title: 僅查看會議體驗
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解適用于系統管理員、簡報者和出席者的 Teams 唯一查看會議體驗
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237453"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 只能查看會議體驗

> [!Note]
> 將于 2021 年 3 月初提供只能觀看的會議體驗。

> [!Note]
> 我們已為 20，000 名出席者暫時增加只能觀看體驗，但我們將在 2021 年 6 月 30 日將支援回復為 10，000 位出席者。

Microsoft Teams 允許最多 10，000 位出席者加入 Teams 會議。 達到主要會議容量後，其他出席者會以只能觀看的體驗加入。

先加入會議的出席者 ，最多可取得會議容量，獲得完整的 Teams 會議體驗。 他們可以共用音訊和視音訊、查看分享的影片，以及參與會議聊天。

在達到主要會議容量後加入的出席者將享有只能觀看的體驗。

我們有完整的 Android 和 iOS 行動支援，讓出席者加入。

> [!Note]
> 在 WW 中，可聊天和通話參與會議人數目前限制為 300 人，GCC、GCC High 和 DoD 為 250 人。

根據預設，任何擁有 E3/E5/A3/A5 SKU 的召集人，都啟用只能觀看的體驗。 無需進一步設定或設定。

### <a name="disable-teams-view-only-experience"></a>停用 Teams 只能查看體驗

系統管理員可以使用 PowerShell 停用只能查看的體驗。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

未來系統管理員也可以停用 Teams 系統管理中心的只能查看體驗。

## <a name="impact-to-users"></a>影響使用者

使用者的體驗會因幾項因素而異。

當達到主要會議容量時，如果下列任一項為 True，出席者將無法加入會議：

- 系統管理員已停用 Teams 只能查看的體驗。
- 出席者沒有避開大廳的許可權。

當達到主要會議容量時，會議召集人和簡報者會看到橫幅，通知他們已達會議容量，且新的出席者將加入只能觀看的出席者。

  ![適用于召集人和簡報者的 Teams 用戶端和橫幅亂七八糟](media/chat-and-banner-message.png)

當達到主要會議容量時，會議出席者在加入前畫面上會通知他們以僅以唯一模式加入。

  ![Teams 加入前畫面，以及參與者的訊息，告知他們將在僅觀看模式中加入](media/view-only-pre-join-screen.png)

如果有空間，使用者一定會加入主要會議。 如果主要會議達到容量，且有一或多個出席者離開主要會議，則主要會議具有可用的容量。 加入會議 (或重新加入會議) 會加入主要會議，直到會議再次到達容量。 只有觀看體驗的出席者不會自動升級至主要會議，目前無法手動升級至主要會議。

如果尚未設定簡報者/出席者角色，主會議的空格會先到先用。 一旦達到會議容量，所有其他使用者就會以只能查看的體驗加入。

## <a name="impact-to-meeting-presenters"></a>對會議簡報者的影響

我們會為會議選項中明確指出為簡報者的使用者保留一般會議空間。 如果簡報者離開，之後又重新加入會議，就會讓他們以簡報者的名加入會議。

會議簡報者的限制包括：

- 您沒有僅查看出席者的資訊。 我們不支援只有視圖的出席者使用 E-discovery。
- 使用者看不到只能查看的出席者。
- 無法從會議移除只能查看的出席者。

> [!Note]
> 出席者計數只會反映會議中的人員，不會反映溢位會議室中的人員。 因此，簡報者無法精確計算誰在只能觀看的體驗中。

## <a name="experience-for-view-only-attendees"></a>僅供觀看的出席者使用體驗

Teams 只能查看體驗可讓出席者：

- 聆聽 Teams 主要會議的參與者。
- 如果使用中喇叭正在分享視 (，請觀看使用中喇叭的視) 。
- 查看使用共用桌面功能共用的內容。

只有看視圖的出席者將無法在會議中體驗下列選項：

- 如果出席者沒有許可權根據設定大廳政策或選項來避開大廳，請加入會議。
- 透過音訊會議加入溢位會議室。
- 透過 Microsoft Teams Room 系統或透過雲端視 (CVI 服務加入溢位) 聊天室。
- 透過 Teams Android 行動應用程式加入溢位會議室。
- 分享他們的音訊或視視。
- 查看或參與會議聊天。
- 除非參與者是活動演講者，否則請觀看會議參與者的影片來源。
- 請參閱使用原生共用 PowerPoint 功能共用的 PowerPoint 檔案，或桌面共用應用程式 (共用物件) 。

## <a name="view-only-feature-limitations"></a>僅查看功能限制

- 不論會議的即時字幕設定如何，只有觀看的出席者一定會看到即時字幕。 目前僅支援英文標題。
- 串流技術將支援只有觀看的出席者。
- 只有查看的出席者不會包含在出席報告中。
- 只有觀看的出席者將擁有單一影片體驗。 他們可以看到使用中的喇叭或共用的內容，但無法同時看到兩者。
- 我們目前不支援圖庫 **、****大型** 圖庫或只供出席者使用共聚模式版面配置。  
- 只有觀看的出席者不會有與一般出席者相同的延遲時間。 <sup>1</sup>

  <sup>1</sup> 只有觀看的出席者在會議進行 30 秒的視像和音訊延遲。  

## <a name="related-topics"></a>相關主題

- [Teams 的進級通訊附加元件](teams-add-on-licensing/advanced-communications.md)
- [Teams 的限制和規格](limits-specifications-teams.md)
