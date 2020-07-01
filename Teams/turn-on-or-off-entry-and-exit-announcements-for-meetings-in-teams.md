---
title: 開啟或關閉小組中會議的進入與結束宣告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在 Microsoft 團隊會議中開啟或關閉 [進入] 和 [結束公告]。
ms.openlocfilehash: ae2e8936b3fe0dbac0ba0d6ad7bfad3ab2e322ef
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938552"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>開啟或關閉 Microsoft 團隊中的會議進入與結束宣告

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您將會收到音訊會議橋。 [會議橋] 可以包含一或多個電話號碼，供人們撥打 Microsoft 團隊會議時使用。 
  
[會議橋接] 會使用電話撥入會議的使用者，接聽來電。 「會議橋接」會使用會議自動語音應答中的語音提示來應答來電者，然後根據您的設定，可以播放通知、要求呼叫者記錄其名稱，以及設定 PIN 安全性。 您可以將 PIN 提供給 Microsoft 團隊會議召集人，如果他們無法使用 Microsoft 團隊 app 來啟動會議，就能讓他們開始會議。 不過，您可以將它設定為不需要 PIN 就能開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>設定會議加入選項

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

您必須是系統管理員，才能進行這些變更。

1. 登入系統管理中心  <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a> 。

2. 在左側導覽中，前往 [**會議**  >  **會議橋**]。 

3. 在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。 

4. 在 [**橋設定**] 窗格中，啟用或停用**會議進入和結束通知**。 預設會選取此選項。 如果您清除此選項，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。
    
5. 在 [**進入/結束宣告類型**] 底下，選取 [**名稱或電話號碼**] 或 [**聲音**]。

   > [!NOTE]
   > 根據預設，外部參與者看不到撥入參與者的電話號碼。 如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型]**** 的 [音調]**** (這可避免 Teams 將號碼朗讀出來)。
    
6. 如果您選擇 [**名稱] 或 [電話號碼**]，請在加入會議前，啟用或停用**要求呼叫者記下其名稱**。
    
7. 按一下 [儲存]****。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。
  
## <a name="related-topics"></a>相關主題

[音訊會議的常見問題](audio-conferencing-common-questions.md)
