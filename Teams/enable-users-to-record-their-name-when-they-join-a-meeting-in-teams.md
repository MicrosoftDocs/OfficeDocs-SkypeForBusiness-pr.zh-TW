---
title: 讓使用者錄製會議的名稱
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解如何啟用或停用使用者是否可以在加入 Microsoft Teams 會議時記錄他們的名稱。
ms.openlocfilehash: 8d626437d1e7dd04ce8b4f91428bfe22cc3aeb43
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641724"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>讓使用者在 Microsoft Teams 中加入會議時記錄他們的名稱

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到電話號碼，以及所謂的音訊會議橋接器。 會議橋接器可以包含一或多個可以是專用或共用電話號碼的電話號碼。
  
會議橋接器會為使用電話撥入會議的使用者接聽電話。 會議橋接器會以自動語音應答的語音提示接聽來電者，然後根據他們的設定播放通知、要求來電者錄下他們的名稱，以及設定會議召集人的 PIN 安全性。 會將 PIN 提供給會議召集人，讓他們開始會議。 不過，您可以進行設定，讓您不需要 PIN 就能召開會議。

## <a name="set-whether-callers-should-record-their-name"></a>設定來電者是否應該記錄他們的名稱

使用 Microsoft Teams 系統管理中心：

1. 在左側導覽中，移至 **[會議**  >  **橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 啟用或停用 **會議進入和結束通知**。

4. 如果啟用通知，請在 [**進入/結束公告類型**] 底下選擇 [**名稱] 或 [電話號碼**]，然後開啟 **[要求來電者在加入會議前記錄他們的名稱]。**

5. 按一下 [儲存]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理Office 365的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參[閱 Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)資訊以取得詳細資訊。
