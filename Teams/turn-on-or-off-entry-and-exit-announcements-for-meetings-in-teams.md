---
title: 開啟或關閉 Teams 中會議的進入和離開公告
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
description: 系統管理員可以瞭解如何在 Microsoft Teams 會議開啟或關閉進入和退出公告。
ms.openlocfilehash: 6be1c6dc86d8088b5ddb54b2141a10172ba13cc5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121331"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中開啟或關閉會議進入和離開公告

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，會取得音訊會議橋接器。 會議橋接器可以包含一或多個電話號碼，使用者會使用該電話號碼來撥打 Microsoft Teams 會議。
  
會議橋接器會針對使用電話撥入會議的使用者接聽電話。 會議橋接器會從會議自動語音應答接聽來電者語音提示，然後視您的設定播放通知、要求來電者錄製其名稱，以及設定 PIN 安全性。 MICROSOFT Teams 會議召集人會提供 PIN，如果無法使用 Microsoft Teams 應用程式開始會議，則 PIN 可讓他們開始會議。 不過，您可以將其設定為不需要 PIN 才能開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>設定會議加入選項

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

您必須是 Teams 服務系統管理員才能進行這些變更。 請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 登入系統管理中心。

2. 在左側流覽中，前往 **會議**  >  **會議橋接器**。

3. 在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。

4. 在橋接器 **設定窗格中** ，啟用或停用 **會議專案及離開通知**。 這是預設選取的。 如果您清除，當某人進入或離開會議時，已加入會議的使用者不會收到通知。

5. 在 **進入/離開公告類型下**，選取名稱 **或電話號碼** 或 **語音**。

   > [!NOTE]
   > 根據預設，外部參與者看不到撥入參與者的電話號碼。 如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。

6. 如果您選擇名稱 **或電話號碼**，請啟用或停用要求來電者在加入會議前 **記錄其名稱**。

7. 按一下 [儲存]。

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell

Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：

- [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))

有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。
  
## <a name="related-topics"></a>相關主題

[音訊會議的常見問題](audio-conferencing-common-questions.md)